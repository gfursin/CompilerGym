workspace(name = "CompilerGym")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# === Google test ===

http_archive(
    name = "gtest",
    sha256 = "9dc9157a9a1551ec7a7e43daea9a694a0bb5fb8bec81235d8a1e6ef64c716dcb",
    strip_prefix = "googletest-release-1.10.0",
    urls = [
        "https://github.com/google/googletest/archive/release-1.10.0.tar.gz",
    ],
)

# === Google benchmark ===

http_archive(
    name = "com_github_google_benchmark",
    sha256 = "616f252f37d61b15037e3c2ef956905baf9c9eecfeab400cb3ad25bae714e214",
    strip_prefix = "benchmark-1.4.0",
    url = "https://github.com/google/benchmark/archive/v1.4.0.tar.gz",
)

# === Google flags ===

http_archive(
    name = "gflags",
    sha256 = "34af2f15cf7367513b352bdcd2493ab14ce43692d2dcd9dfc499492966c64dcf",
    strip_prefix = "gflags-2.2.2",
    urls = ["https://github.com/gflags/gflags/archive/v2.2.2.tar.gz"],
)

# === Google logging ===

http_archive(
    name = "glog",
    sha256 = "f28359aeba12f30d73d9e4711ef356dc842886968112162bc73002645139c39c",
    strip_prefix = "glog-0.4.0",
    urls = ["https://github.com/google/glog/archive/v0.4.0.tar.gz"],
)

# === LLVM ===

http_archive(
    name = "llvm",
    sha256 = "47744dbbbe01f107682503348cb570c771152e44d9c75b7f45cf17dc2711ee7d",
    strip_prefix = "bazel_llvm-9481d3c85247bbc284d8283aa5b6b8b517301262",
    urls = ["https://github.com/ChrisCummins/bazel_llvm/archive/9481d3c85247bbc284d8283aa5b6b8b517301262.tar.gz"],
)

load("@llvm//tools/bzl:deps.bzl", "llvm_deps")

llvm_deps()

# === Building CMake projects ===

http_archive(
    name = "rules_foreign_cc",
    sha256 = "dd2ccc6ad7227d36586f6bb3efe9bdf8b2b247bd420e36fdc19345369057d991",
    strip_prefix = "rules_foreign_cc-660ed328733bbc38e03f4b4949f05a14e3eaea4e",
    url = "https://github.com/ChrisCummins/rules_foreign_cc/archive/660ed328733bbc38e03f4b4949f05a14e3eaea4e.zip",
)

load("@rules_foreign_cc//:workspace_definitions.bzl", "rules_foreign_cc_dependencies")

rules_foreign_cc_dependencies([])

# === Python rules ===

http_archive(
    name = "rules_python",
    sha256 = "b5668cde8bb6e3515057ef465a35ad712214962f0b3a314e551204266c7be90c",
    strip_prefix = "rules_python-0.0.2",
    url = "https://github.com/bazelbuild/rules_python/releases/download/0.0.2/rules_python-0.0.2.tar.gz",
)

load("@rules_python//python:repositories.bzl", "py_repositories")

py_repositories()

# === Protocol buffers ===

http_archive(
    name = "rules_proto",
    sha256 = "8e7d59a5b12b233be5652e3d29f42fba01c7cbab09f6b3a8d0a57ed6d1e9a0da",
    strip_prefix = "rules_proto-7e4afce6fe62dbff0a4a03450143146f9f2d7488",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_proto/archive/7e4afce6fe62dbff0a4a03450143146f9f2d7488.tar.gz",
        "https://github.com/bazelbuild/rules_proto/archive/7e4afce6fe62dbff0a4a03450143146f9f2d7488.tar.gz",
    ],
)

load("@rules_proto//proto:repositories.bzl", "rules_proto_dependencies", "rules_proto_toolchains")

rules_proto_dependencies()

rules_proto_toolchains()

# === GRPC ===

http_archive(
    name = "com_github_grpc_grpc",
    sha256 = "7372a881122cd85a7224435a1d58bc5e11c88d4fb98a64b83f36f3d1c2f16d39",
    strip_prefix = "grpc-1.34.0",
    urls = [
        "https://github.com/grpc/grpc/archive/v1.34.0.tar.gz",
    ],
)

load("@com_github_grpc_grpc//bazel:grpc_deps.bzl", "grpc_deps")

grpc_deps()

load("@com_github_grpc_grpc//bazel:grpc_extra_deps.bzl", "grpc_extra_deps")

grpc_extra_deps()

# === C++ enum trickery ===
# https://github.com/Neargye/magic_enum

http_archive(
    name = "magic_enum",
    build_file_content = """
cc_library(
    name = "magic_enum",
    hdrs = ["include/magic_enum.hpp"],
    includes = ["include"],
    visibility = ["//visibility:public"],
)
""",
    sha256 = "c7e96ad8bd260a831a59d2779ab8ceb9f1a056da177fdb5a3fec538cfaac9d52",
    strip_prefix = "magic_enum-6e932ef66dbe054e039d4dba77a41a12f9f52e0c",
    urls = ["https://github.com/Neargye/magic_enum/archive/6e932ef66dbe054e039d4dba77a41a12f9f52e0c.tar.gz"],
)

# === ctuning-programs ===
# https://github.com/ChrisCummins/ctuning-programs

http_archive(
    name = "ctuning-programs",
    build_file_content = """
filegroup(
    name = "all",
    srcs = glob(["**"]),
    visibility = ["//visibility:public"],
)

filegroup(
    name = "readme",
    srcs = ["README.md"],
    visibility = ["//visibility:public"],
)
""",
    sha256 = "5e14a49f87c70999a082cb5cf19b780d0b56186f63356f8f994dd9ffc79ec6f3",
    strip_prefix = "ctuning-programs-c3c126fcb400f3a14b69b152f15d15eae78ef908",
    urls = ["https://github.com/ChrisCummins/ctuning-programs/archive/c3c126fcb400f3a14b69b152f15d15eae78ef908.tar.gz"],
)

# === cBench ===
# https://ctuning.org/wiki/index.php/CTools:CBench

all_content = """filegroup(name = "all", srcs = glob(["**"]), visibility = ["//visibility:public"])"""

http_archive(
    name = "cBench",
    build_file_content = """
filegroup(
    name = "all",
    srcs = glob(["**"]),
    visibility = ["//visibility:public"],
)

filegroup(
    name = "readme",
    srcs = ["README-cBench-V1.1.txt"],
    visibility = ["//visibility:public"],
)
""",
    sha256 = "8908d742f5223f09f9a4d10f7e06bc805a0c1694aa70974d2aae91ab627b51e6",
    urls = ["https://downloads.sourceforge.net/project/cbenchmark/cBench/V1.1/cBench_V1.1.tar.gz"],
)

http_archive(
    name = "cBench_network_dijkstra_data",
    build_file_content = all_content,
    urls = ["https://downloads.sourceforge.net/project/cbenchmark/cDatasets/V1.1/cDatasets_V1.1_network_dijkstra_data.tar.gz"],
)

# === C++ cpuinfo ===

http_archive(
    name = "cpuinfo",
    build_file_content = all_content,
    sha256 = "18a99130ced1eaacab2ba8f75a1435f9955aab54fa0436b60468f020876ee902",
    strip_prefix = "cpuinfo-63b254577ed77a8004a9be6ac707f3dccc4e1fd9",
    urls = ["https://github.com/pytorch/cpuinfo/archive/63b254577ed77a8004a9be6ac707f3dccc4e1fd9.tar.gz"],
)

# === DeepDataFlow ===
# https://zenodo.org/record/4122437

http_archive(
    name = "DeepDataFlow",
    build_file = "//:third_party/DeepDataFlow/DeepDataFlow.BUILD",
    sha256 = "ea6accbeb005889db3ecaae99403933c1008e0f2f4adc3c4afae3d7665c54004",
    urls = ["https://zenodo.org/record/4122437/files/llvm_bc_20.06.01.tar.bz2?download=1"],
)

# === A modern C++ formatting library ===
# https://fmt.dev

http_archive(
    name = "fmt",
    build_file_content = """
cc_library(
    name = "fmt",
    srcs = glob(["src/*.cc"]),
    hdrs = glob(["include/fmt/*.h"]),
    copts = ["-Iexternal/fmt/include"],
    strip_include_prefix = "include",
    visibility = ["//visibility:public"],
)
""",
    sha256 = "1cafc80701b746085dddf41bd9193e6d35089e1c6ec1940e037fcb9c98f62365",
    strip_prefix = "fmt-6.1.2",
    urls = ["https://github.com/fmtlib/fmt/archive/6.1.2.tar.gz"],
)

# === Boost ===
# https://github.com/nelhage/rules_boost

http_archive(
    name = "com_github_nelhage_rules_boost",
    sha256 = "4031539fe0af832c6b6ed6974d820d350299a291ba7337d6c599d4854e47ed88",
    strip_prefix = "rules_boost-4ee400beca08f524e7ea3be3ca41cce34454272f",
    urls = ["https://github.com/nelhage/rules_boost/archive/4ee400beca08f524e7ea3be3ca41cce34454272f.tar.gz"],
)

load("@com_github_nelhage_rules_boost//:boost/boost.bzl", "boost_deps")

boost_deps()

# === ProGraML ===
# https://github.com/ChrisCummins/ProGraML

http_archive(
    name = "programl",
    sha256 = "5a8fc6f71f1971b265cfe0c4b224b45e87ef08e40b49e693a96022063345a9c8",
    strip_prefix = "ProGraML-0476300f2db3724c7b6ecd10970b4525fccc8628",
    urls = ["https://github.com/ChrisCummins/ProGraML/archive/0476300f2db3724c7b6ecd10970b4525fccc8628.tar.gz"],
)

load("@programl//tools:bzl/deps.bzl", "programl_deps")

programl_deps()
