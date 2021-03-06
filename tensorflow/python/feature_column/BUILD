package(
    default_visibility = ["//tensorflow:internal"],
)

licenses(["notice"])  # Apache 2.0

load("//tensorflow:tensorflow.bzl", "tf_py_test")

py_library(
    name = "feature_column_py",
    srcs = ["feature_column_lib.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":feature_column",
        ":feature_column_v2",
        ":sequence_feature_column",
        "//tensorflow/python:util",
    ],
)

py_library(
    name = "feature_column",
    srcs = ["feature_column.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":utils",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:check_ops",
        "//tensorflow/python:control_flow_ops",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:embedding_ops",
        "//tensorflow/python:framework_ops",
        "//tensorflow/python:init_ops",
        "//tensorflow/python:layers_base",
        "//tensorflow/python:lookup_ops",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:nn_ops",
        "//tensorflow/python:parsing_ops",
        "//tensorflow/python:platform",
        "//tensorflow/python:resource_variable_ops",
        "//tensorflow/python:sparse_ops",
        "//tensorflow/python:sparse_tensor",
        "//tensorflow/python:string_ops",
        "//tensorflow/python:template",
        "//tensorflow/python:tensor_shape",
        "//tensorflow/python:training",
        "//tensorflow/python:util",
        "//tensorflow/python:variable_scope",
        "//tensorflow/python:variables",
        "//tensorflow/python/keras",
        "@six_archive//:six",
    ],
)

py_library(
    name = "feature_column_v2",
    srcs = ["feature_column_v2.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":feature_column",
        ":utils",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:check_ops",
        "//tensorflow/python:control_flow_ops",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:embedding_ops",
        "//tensorflow/python:framework_ops",
        "//tensorflow/python:init_ops",
        "//tensorflow/python:lookup_ops",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:nn_ops",
        "//tensorflow/python:parsing_ops",
        "//tensorflow/python:platform",
        "//tensorflow/python:resource_variable_ops",
        "//tensorflow/python:sparse_ops",
        "//tensorflow/python:sparse_tensor",
        "//tensorflow/python:string_ops",
        "//tensorflow/python:template",
        "//tensorflow/python:tensor_shape",
        "//tensorflow/python:training",
        "//tensorflow/python:util",
        "//tensorflow/python:variable_scope",
        "//tensorflow/python:variables",
        "//tensorflow/python/keras",
        "//third_party/py/numpy",
        "@six_archive//:six",
    ],
)

filegroup(
    name = "vocabulary_testdata",
    srcs = [
        "testdata/embedding.ckpt.data-00000-of-00001",
        "testdata/embedding.ckpt.index",
        "testdata/embedding.ckpt.meta",
        "testdata/warriors_vocabulary.txt",
        "testdata/wire_vocabulary.txt",
    ],
)

tf_py_test(
    name = "feature_column_test",
    srcs = ["feature_column_test.py"],
    additional_deps = [
        ":feature_column",
        ":feature_column_py",
        "//third_party/py/numpy",
        "//tensorflow/core:protos_all_py",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:constant_op",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:errors",
        "//tensorflow/python:framework_ops",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:lookup_ops",
        "//tensorflow/python:parsing_ops",
        "//tensorflow/python:partitioned_variables",
        "//tensorflow/python:session",
        "//tensorflow/python:sparse_tensor",
        "//tensorflow/python:training",
        "//tensorflow/python:variable_scope",
        "//tensorflow/python:variables",
        "//tensorflow/python/eager:backprop",
        "//tensorflow/python/eager:context",
    ],
    data = [":vocabulary_testdata"],
    tags = [
        "no_cuda_on_cpu_tap",
        "no_pip",
        "no_windows",
    ],
)

tf_py_test(
    name = "feature_column_v2_test",
    srcs = ["feature_column_v2_test.py"],
    additional_deps = [
        ":feature_column_py",
        ":feature_column_v2",
        "//third_party/py/numpy",
        "//tensorflow/core:protos_all_py",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:constant_op",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:errors",
        "//tensorflow/python:framework_ops",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:lookup_ops",
        "//tensorflow/python:parsing_ops",
        "//tensorflow/python:partitioned_variables",
        "//tensorflow/python:session",
        "//tensorflow/python:sparse_tensor",
        "//tensorflow/python:training",
        "//tensorflow/python:variable_scope",
        "//tensorflow/python:variables",
        "//tensorflow/python/eager:backprop",
        "//tensorflow/python/eager:context",
        "//tensorflow/python/estimator:estimator_py",
    ],
    data = [":vocabulary_testdata"],
    shard_count = 5,
    tags = [
        "no_cuda_on_cpu_tap",
        "no_pip",
        "no_windows",
    ],
)

py_library(
    name = "sequence_feature_column",
    srcs = ["sequence_feature_column.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":feature_column_v2",
        ":utils",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:check_ops",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:framework_ops",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:parsing_ops",
        "//tensorflow/python:sparse_ops",
        "//tensorflow/python:tensor_shape",
        "//tensorflow/python:variable_scope",
    ],
)

py_library(
    name = "utils",
    srcs = ["utils.py"],
    srcs_version = "PY2AND3",
    deps = [
        "//tensorflow/python:array_ops",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:framework_ops",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:util",
    ],
)

tf_py_test(
    name = "sequence_feature_column_test",
    srcs = ["sequence_feature_column_test.py"],
    additional_deps = [
        ":feature_column_v2",
        ":feature_column_v2_test",
        ":sequence_feature_column",
        "@absl_py//absl/testing:parameterized",
        "//third_party/py/numpy",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:dtypes",
        "//tensorflow/python:errors",
        "//tensorflow/python:framework_ops",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:parsing_ops",
        "//tensorflow/python:sparse_tensor",
        "//tensorflow/python:training",
    ],
    tags = ["no_pip"],
)

py_test(
    name = "sequence_feature_column_integration_test",
    srcs = ["sequence_feature_column_integration_test.py"],
    srcs_version = "PY2AND3",
    tags = ["no_pip"],
    deps = [
        ":feature_column_v2",
        ":sequence_feature_column",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_ops",
        "//tensorflow/python:parsing_ops",
        "//tensorflow/python:training",
        "//tensorflow/python:util",
        "//tensorflow/python/keras:layers",
    ],
)
