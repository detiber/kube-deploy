load("@io_bazel_rules_go//proto:def.bzl", "go_grpc_library")
load("@io_bazel_rules_go//go:def.bzl", "go_library")

go_library(
    name = "go_default_library",
    srcs = [
        "etcdserver.pb.go",
        "raft_internal.pb.go",
        "rpc.pb.go",
        "rpc.pb.gw.go",
    ],
    importpath = "github.com/coreos/etcd/etcdserver/etcdserverpb",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/coreos/etcd/auth/authpb:go_default_library",
        "//vendor/github.com/coreos/etcd/mvcc/mvccpb:go_default_library",
        "//vendor/github.com/golang/protobuf/proto:go_default_library",
        "//vendor/github.com/grpc-ecosystem/grpc-gateway/runtime:go_default_library",
        "//vendor/github.com/grpc-ecosystem/grpc-gateway/utilities:go_default_library",
        "//vendor/golang.org/x/net/context:go_default_library",
        "//vendor/google.golang.org/grpc:go_default_library",
        "//vendor/google.golang.org/grpc/codes:go_default_library",
        "//vendor/google.golang.org/grpc/grpclog:go_default_library",
    ],
)

proto_library(
    name = "etcdserverpb_proto",
    srcs = [
        "etcdserver.proto",
        "raft_internal.proto",
        "rpc.proto",
    ],
    visibility = ["//visibility:public"],
    deps = [
        "//:apiserver-builder_proto",
        "//etcd/auth/authpb:authpb_proto",
        "//etcd/mvcc/mvccpb:mvccpb_proto",
        "//gogoproto:gogoproto_proto",
        "//google/api:api_proto",
    ],
)

go_grpc_library(
    name = "etcdserverpb_go_proto",
    importpath = "github.com/coreos/etcd/etcdserver/etcdserverpb",
    proto = ":etcdserverpb_proto",
    visibility = ["//visibility:public"],
    deps = [
        "//:go_default_library",
        "//etcd/auth/authpb:go_default_library",
        "//etcd/mvcc/mvccpb:go_default_library",
        "//gogoproto:go_default_library",
        "//google/api:go_default_library",
    ],
)
