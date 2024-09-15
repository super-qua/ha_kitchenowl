# Kitchenowl for Home Assistant

## Low Maintentance Project
This project is a low maintenance project. The scope is purposefully kept narrow and I am not looking to extend this beyond its current scope.
For this reason, issues and discussions are not activated for this project. Feel free to fork the project in case you feel like a functionality is missing.

## Installation
This is not currently available in HACS, and the python package required is also not published on PyPi at the moment.
To manually install the integration in your local Home Assistant instance

1. Clone the repository locally
2. Init `kitchenowl_python` submodule
```bash
git checkout submodule
git submodule init
git submodule update
```
3. zip the `ha_kitchenowl/custom_components/kitchenowl` folder
4. Upload the zip to your instance to the `custom_components` folder
    - for example with the [File Editor Add-on](https://github.com/home-assistant/addons/tree/master/configurator)
5. Unzip the file
    - you can use the [Advanced SSH & Web Terminal Add-on](https://github.com/hassio-addons/addon-ssh) for this
```bash
cd config/custom_compontents
unzip kitchenowl.zip
rm kitchenowl.zip
```
6. Restart Home Assistant
7. Set up the integration
    - Go to Settings > Devices & Services
    - Add Integration
8. Fill in your KitchenOwl settings
    - The IP / URL of your KitchenOwl instance
    - The Access Token (can be set up in your KitchenOwl Profile > Sessions)
9. Select the household

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
