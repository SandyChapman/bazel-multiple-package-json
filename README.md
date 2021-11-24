# Problem:

Run

```
bazel build //devtools:pyright
```

Result:

Both node_modules directories get built when there is no dependency on `@npm`