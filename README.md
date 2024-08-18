# Portable Bazel Rules for GLFW and GLM

This repository provides portable Bazel rules for integrating **GLFW** and **GLM** into your cross-platform C++ projects. It supports Windows, macOS, and Linux.

## Getting Started

### Integration

Simply include the libraries `glfw`, `glm`, or `glm_header_only` in your Bazel `BUILD` files to integrate them into your binaries.

```python
cc_binary(
    name = "my_app",
    srcs = ["main.cpp"],
    deps = [
        "//:glfw",
        "//:glm",
        # or "//:glm_header_only"
    ],
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
