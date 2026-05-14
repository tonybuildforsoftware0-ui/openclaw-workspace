# ERRORS.md

## 2026-04-27
- Desktop automation blocked by headless server (need Xvfb).

## 2026-05-09
- Python one-liner skill readiness check failed twice due nested f-string/newline quoting inside `python3 -c`; use a single-line list comprehension with simple string concatenation instead.

## 2026-05-12
- `qmd status` printed index status but exited nonzero while trying to build node-llama-cpp Vulkan support because Vulkan libraries/includes/glslc are missing; treat QMD as usable on CPU but avoid assuming a clean zero exit until Vulkan/GPU support is fixed or disabled.
