# Configuration

Toutes les actions dans Play! utilise le pool de Thread par défaut.

Ce pool est configuré comme suit :

```
akka {
  actor {
    default-dispatcher {
      fork-join-executor {
        # Settings this to 1 instead of 3 seems to improve performance.
        parallelism-factor = 1.0

        # @richdougherty: Not sure why this is set below the Akka
        # default.
        parallelism-max = 24

        # Setting this to LIFO changes the fork-join-executor
        # to use a stack discipline for task scheduling. This usually
        # improves throughput at the cost of possibly increasing
        # latency and risking task starvation (which should be rare).
        task-peeking-mode = LIFO
      }
    }
  }
}
```

Source: https://www.playframework.com/documentation/2.6.x/ThreadPools#configuring-the-default-thread-pool

