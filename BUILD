load("@buckaroo//:defs.bzl", "buckaroo_workspace")

a = "@" + buckaroo_workspace("github.com/njlr/bazel-test-a") + "//:a"
b = "@" + buckaroo_workspace("github.com/njlr/bazel-test-b") + "//:b"
c = "@" + buckaroo_workspace("github.com/njlr/bazel-test-c") + "//:c"

cc_library(
  name = "d",
  includes = [
    "include",
  ],
  hdrs = glob([
    "include/*.hpp",
  ]),
  srcs = glob([
    "include/*.hpp",
    "src/*.cpp",
  ]),
  deps = [
    a,
    c,
  ],
  visibility = [
    "//visibility:public",
  ],
)

cc_binary(
  name = "app",
  srcs = [
    "main.cpp",
  ],
  deps = [
    a,
    b,
    c,
    ":d",
  ],
)
