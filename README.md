<h1 align="center"><b>Flash Attention index</b></h1>
<h3 align="center">PEP 503 indexes for flash-attention prebuilt wheels.</h3>

These indexes provide prebuilt wheels for `flash-attn` to speed up installation and avoid compilation issues. The wheels are prebuilt and provided by [@mjun0812](https://github.com/mjun0812/flash-attention-prebuild-wheels)
(and a few others by [me](https://github.com/codcordance/flash-attention-win))


## Usage

You can use these indexes to easily install `flash-attn` with tools that support PEP 503 indexes, such as `uv`, `poetry`, or standard `pip`.

### `uv` (in `pyproject.toml`)

```toml
[tool.uv.sources]
flash-attn = [{index = "flash-attn-cu130", marker = "sys_platform == 'linux' or sys_platform == 'win32'" }]

[[tool.uv.index]]
name = "flash-attn-cu130"
url = "https://codcordance.github.io/flash-attn-index/cu130/"
explicit = true
```

### `poetry` (in `pyproject.toml`)

```toml
[[tool.poetry.source]]
name = "flash-attn-cu130"
url = "https://codcordance.github.io/flash-attn-index/cu130/"
priority = "explicit"

[tool.poetry.dependencies]
flash-attn = { version = "*", source = "flash-attn-cu130", markers = "sys_platform == 'linux' or sys_platform == 'win32'" }
```

### `pip`

```bash
pip install flash-attn --extra-index-url https://codcordance.github.io/flash-attn-index/cu130/
```

*(Note: Replace `cu130` with `cu126` or `cu128` in the URLs and index names depending on your CUDA version requirements.)*