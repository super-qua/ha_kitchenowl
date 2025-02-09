# Kitchenowl for Home Assistant

> [!NOTE]
> This repository is no longer maintained. Please refer to the official fork on https://github.com/TomBursch/kitchenowl-ha

## Development

Set up the local development environment according to https://developers.home-assistant.io/docs/development_environment

### Clone this repo
Make sure to run
```bash
git submodule init
git submodule update
```

### Mount the local directory
Add this to the `devcontainer.json` to mount your local directory with ha_kitchenowl into the container

```json
"mounts":[
    "source=<your_path>/kitchenowl/custom_components,target=/workspaces/home-assistant-core/config/custom_components,type=bind,consistency=cached"
]
```

### Install `kitchenowl_python` package

Until `kitchenowl_python` is published on PyPi, install the submodule with

```bash
python3 -m pip install -e config/custom_components/kitchenowl/kitchenowl_python/
```
from the Terminal in VS Code.
