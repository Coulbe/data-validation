licenses(["notice"])  # Apache 2.0

config_setting(
    name = "windows",
    constraint_values = [
        "@bazel_tools//platforms:windows",
    ],
)

sh_binary(
    name = "build_pip_package",
    srcs = ["build_pip_package.sh"],
    data = select({
        ":windows": [
            "//tensorflow_data_validation/anomalies/proto:validation_config_pb2.py",
            "//tensorflow_data_validation/anomalies/proto:validation_metadata_pb2.py",
            "//tensorflow_data_validation/pywrap:tensorflow_data_validation_extension.pyd",
        ],
        "//conditions:default": [
            "//tensorflow_data_validation/anomalies/proto:validation_config_pb2.py",
            "//tensorflow_data_validation/anomalies/proto:validation_metadata_pb2.py",
            "//tensorflow_data_validation/pywrap:tensorflow_data_validation_extension.so",
        ],
    }),
)
