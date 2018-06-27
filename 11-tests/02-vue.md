# Tester une vue

* Créer un test unitaire pour la vue `views.html.inbox` :


```java
public class InboxTemplateTest {


    @Test
    public void test_inbox_list() {

        Http.Context.current.set(Helpers.httpContext());

        List<InboxItem> inboxItems = TestHelpers.buildInboxes("A", "B", "C");

        Html html = views.html.inbox.render(inboxItems);
        String page = Helpers.contentAsString(html);

        // TODO ajouter une assertion


    }
}

```

Code de la classe TestHelpers :

```java
package helpers;

import models.InboxItem;

import java.util.List;
import java.util.UUID;
import java.util.stream.Collectors;
import java.util.stream.Stream;

public class TestHelpers {

    public static InboxItem buildInboxItem(String title, String url, String note) {
        InboxItem inboxItem = new InboxItem();
        inboxItem.setId(UUID.randomUUID());
        inboxItem.setTitle(title);
        inboxItem.setNote(note);
        inboxItem.setUrl(url);
        return inboxItem;
    }

    public static List<InboxItem> buildInboxes(String... variants) {

        return Stream.of(variants)
                .map(v -> buildInboxItem("title " + v, "url " + v, "note " + v))
                .collect(Collectors.toList());
    }

}

```