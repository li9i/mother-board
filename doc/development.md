# Development

## Clone

Clone with the hooks enabled:

```bash
git clone -c core.hooksPath=hooks https://github.com/li9i/mother-board
```

The hooks write the build mark. The mark is the short hash of the commit of this copy of the page, below the board. If you cloned without the hooks, `git config core.hooksPath hooks` enables them. The mark then shows after the next commit, merge or checkout.

For more information, refer to [behaviour.md](behaviour.md#build-mark).

## Tests

For how to run the tests and what each test checks, refer to [tests.md](tests.md).
