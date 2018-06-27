# Test avec un contexte application et Mock


* Ajouter Mockito au projet

```
libraryDependencies += "org.mockito" % "mockito-core" % "2.19.0" % Test
```

* Créer une classe de test pour le contrôleur : `InboxApiController`.

```java
public class InboxApiControllerTest extends WithApplication {

    private InboxItemService inboxItemService;

    @Override
    protected Application provideApplication() {
        
        // mock est issu de la librairie Mockito
        this.inboxItemService = mock(InboxItemService.class);

        Application app = new GuiceApplicationBuilder()
                .overrides(binder -> {
                    binder.bind(InboxItemService.class).toInstance(inboxItemService);
                })
                .configure(ConfigFactory.parseResources("application.test.conf"))
                .build();


        return app;
    }


    @Test
    public void test_get_json() {
        Http.RequestBuilder request = new Http.RequestBuilder()
                .method(GET)
                .header("Accept", Http.MimeTypes.JSON)
                .uri(routes.InboxApiController.get().path());


        when(this.inboxItemService.findAll()).thenReturn(
                CompletableFuture.completedFuture(
                        TestHelpers.buildInboxes("a", "b", "c")
                )
        );

        Result result = route(app, request);

        assertThat(result.status()).isEqualTo(OK);
        assertThat(result.body().contentType().get()).isEqualTo(Http.MimeTypes.JSON);
        JsonNode jsonNode = Json.parse(contentAsString(result));

        List<String> titles = jsonNode.findValuesAsText("title");

        assertThat(titles).contains("title a", "title b", "title c");

    }

}
```