load("@io_bazel_rules_go//go:def.bzl", "go_library")
load("@io_bazel_rules_go//proto:def.bzl", "go_proto_library")
load("@rules_proto//proto:defs.bzl", "proto_library")

proto_library(
    name = "helloworld_proto",
    srcs = ["helloworld.proto"],
    visibility = ["//visibility:public"],
)

go_proto_library(
    name = "helloworld_go_proto",
    compilers = ["@io_bazel_rules_go//proto:go_grpc"],
    importpath = "examples/grpc/protos",
    proto = ":helloworld_proto",
    visibility = ["//visibility:public"],
)

go_library(
    name = "protos",
    embed = [":helloworld_go_proto"],
    importpath = "examples/grpc/protos",
    visibility = ["//visibility:public"],
)
