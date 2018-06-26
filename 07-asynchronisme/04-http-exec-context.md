# HttpExecutionContext

```java
import play.libs.concurrent.HttpExecutionContext;
import play.mvc.*;

import javax.inject.Inject;
import java.util.concurrent.CompletableFuture;
import java.util.concurrent.CompletionStage;

public class MyController extends Controller {

    private HttpExecutionContext httpExecutionContext;

    @Inject
    public MyController(HttpExecutionContext ec) {
        this.httpExecutionContext = ec;
    }

    public CompletionStage<Result> index() {
        // Use a different task with explicit EC
        return calculateResponse().thenApplyAsync(answer -> {
            // uses Http.Context
            ctx().flash().put("info", "Response updated!");
            return ok("answer was " + answer);
        }, httpExecutionContext.current());
    }

    private static CompletionStage<String> calculateResponse() {
        return CompletableFuture.completedFuture("42");
    }
}
```

Source : https://www.playframework.com/documentation/2.6.x/ThreadPools