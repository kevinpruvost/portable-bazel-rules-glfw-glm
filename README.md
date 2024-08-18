# Portable Bazel Rules for GLFW and GLM

This repository provides portable Bazel rules for integrating **GLFW** and **GLM** into your cross-platform C++ projects. It supports Windows, macOS, and Linux.

## Getting Started

### Integration

Simply include the libraries `glfw`, `glm`, or `glm_header_only` in your Bazel `BUILD` files to integrate them into your binaries.

If you don't need GLFW to be dynamic, DO NOT FORGET to disable the preprocessor macros _GLFW_BUILD_DLL in `GLFW/BUILD`.

```python
cc_binary(
    name = "my_app",
    srcs = ["main.cpp"],
    copts = [
# Disable if you want to use GLFW as a static library
        "-DGLFW_DLL",
    ],
    deps = [
        "//:glfw_static",
        "//:glm",
        # or "//:glm_header_only"
    ],
)

# if you need 
cc_shared_binary(
    name = "my_app_shared",
    visibility = ["//visibility:public"],
    deps = [
        ":my_app"
    ],
    dynamic_deps = [
        "//:glfw"
    ]
)
```

You can also check my [Computer Graphcis project on Vulkan & Metal using Bazel](https://github.com/kevinpruvost/Bazel_Vulkan_Metal) if you get any problems as I use GLFW and glm.

### Platform Support

- **Windows**: Fully supported.
- **macOS**: Fully supported.
- **Linux**: Built for X11. You can easily tweak the build for Wayland or other configurations if needed.

## Versions

- **GLFW**: Based on [version 3.4](https://github.com/glfw/glfw/releases/tag/3.4)
- **GLM**: Based on [version 1.0.1](https://github.com/g-truc/glm/releases/tag/1.0.1)

## Acknowledgments

Special thanks to the developers of:

- **GLFW**: [https://github.com/glfw/glfw](https://github.com/glfw/glfw)
- **GLM**: [https://github.com/g-truc/glm](https://github.com/g-truc/glm)
