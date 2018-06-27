# Tester de l'extérieur de l'application

Notre classe de test peut hériter au choix de 2 classes :

* `WithServer` : l'application est démarrée et le test envoie des requêtes Http
* `WithBrowser` : l'application est démarrée et un test sélénium est lancé.
Le script est écrit avec https://github.com/FluentLenium/FluentLenium.


* Créer un test de navigation dans l'application :

```java
public class ScenarioInboxTest extends WithBrowser {


    @Test
    public void test_get_json() {

        browser.goTo("/");

        FluentWebElement gBtn = browser.$("#goToInbox").first();
        gBtn.click();

        String url = browser.url();
        assertThat(url).contains("inbox/list");

        // TODO adapter le test

    }

}


```