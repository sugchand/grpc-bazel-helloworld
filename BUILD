load("@bazel_gazelle//:def.bzl", "gazelle")
load("@io_bazel_rules_go//go:def.bzl", "go_path")

#gazelle:prefix github.com/sugchand/grpc-hello-bazel
gazelle(name = "gazelle")

go_path(
    name = "gopath",
    mode = "link",
    deps = [
        "//helloworld:helloworld_go_proto",
        "//greeter_client:greeter_client",
        "//greeter_server:greeter_server",
        ],
)
