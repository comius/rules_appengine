# A target to ensure the servlet-api is not linked in the webapp.
load("@bazel_tools//tools/jdk:default_java_toolchain.bzl", "JDK8_JVM_OPTS", "JVM8_TOOLCHAIN_CONFIGURATION", "default_java_toolchain")

java_library(
    name = "javax.servlet.api",
    neverlink = 1,
    visibility = ["//visibility:public"],
    exports = ["@javax_servlet_api//jar"],
)

filegroup(
    name = "srcs",
    srcs = glob(["**"]),
    visibility = ["//tools:__pkg__"],
)

default_java_toolchain(
    name = "jdk8",
    configuration = JVM8_TOOLCHAIN_CONFIGURATION,
    jvm_opts = JDK8_JVM_OPTS + [
        "-XX:+TieredCompilation",
        "-XX:TieredStopAtLevel=1",
    ],
    source_version = "8",
    target_version = "8",
    visibility = ["//visibility:public"],
)
