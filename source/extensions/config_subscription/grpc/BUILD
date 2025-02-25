load(
    "//bazel:envoy_build_system.bzl",
    "envoy_cc_extension",
    "envoy_cc_library",
    "envoy_extension_package",
)

licenses(["notice"])  # Apache 2

envoy_extension_package()

envoy_cc_library(
    name = "grpc_subscription_impl_lib",
    srcs = ["grpc_subscription_impl.cc"],
    hdrs = ["grpc_subscription_impl.h"],
    deps = [
        "//envoy/config:subscription_interface",
        "//envoy/event:dispatcher_interface",
        "//envoy/grpc:async_client_interface",
        "//source/common/config:custom_config_validators_lib",
        "//source/common/config:grpc_mux_lib",
        "//source/common/config:new_grpc_mux_lib",
        "//source/common/config:type_to_endpoint_lib",
        "//source/common/config:xds_resource_lib",
        "//source/common/config/xds_mux:grpc_mux_lib",
    ],
)

envoy_cc_extension(
    name = "grpc_collection_subscription_lib",
    srcs = ["grpc_collection_subscription_factory.cc"],
    hdrs = ["grpc_collection_subscription_factory.h"],
    extra_visibility = [
        # previously considered core code.
        "//test:__subpackages__",
    ],
    deps = [
        ":grpc_subscription_impl_lib",
        "//envoy/config:subscription_interface",
        "//envoy/event:dispatcher_interface",
        "//source/common/common:minimal_logger_lib",
        "//source/common/common:utility_lib",
        "//source/common/config:custom_config_validators_lib",
        "//source/common/config:decoded_resource_lib",
        "//source/common/config:type_to_endpoint_lib",
        "//source/common/config:utility_lib",
        "//source/common/config:watched_directory_lib",
        "//source/common/protobuf",
        "//source/common/protobuf:message_validator_lib",
        "//source/common/protobuf:utility_lib",
    ],
)

envoy_cc_extension(
    name = "grpc_subscription_lib",
    srcs = ["grpc_subscription_factory.cc"],
    hdrs = ["grpc_subscription_factory.h"],
    extra_visibility = [
        # previously considered core code.
        "//test:__subpackages__",
    ],
    deps = [
        ":grpc_subscription_impl_lib",
        "//envoy/config:subscription_interface",
        "//envoy/event:dispatcher_interface",
        "//source/common/common:minimal_logger_lib",
        "//source/common/common:utility_lib",
        "//source/common/config:custom_config_validators_lib",
        "//source/common/config:decoded_resource_lib",
        "//source/common/config:type_to_endpoint_lib",
        "//source/common/config:utility_lib",
        "//source/common/config:watched_directory_lib",
        "//source/common/protobuf",
        "//source/common/protobuf:message_validator_lib",
        "//source/common/protobuf:utility_lib",
    ],
)
