package(default_visibility = ["//visibility:public"])

load("@tools_npm//pyright:index.bzl", "pyright")

pyright(
    name = "pyright",
)

load("//:foo.bzl", "foo_binary")

foo_binary(name = "bin")