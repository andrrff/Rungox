## Quickstart

- Clone the repository

```bash
gh repo clone GozoDeAvestruz/Rungox
cd Rungox
```

- Build and run the project

```bash
cargo run
```

#### For Mac Users

This starter uses vulkan as a renderer by default. You'll want to change the backend to use `metal`, which can be done by opening the `Cargo.toml` file and changing

```toml
[features]
default = ["vulkan"]
```

to

```toml
[features]
default = ["metal"]
```

If using OSX and Metal you will require full XCode installed from the Appstore in order to compile metal shaders.
After install you may be required to run this command `sudo xcode-select --switch /Applications/Xcode.app/Contents/Developer` [reference gfx-rs issue](https://github.com/gfx-rs/gfx/issues/2472)

#### For Linux Users

You might need to install some dependencies. Please refer to [this section](https://github.com/amethyst/amethyst#dependencies) of the README for more details.

## Features

This project contains the minimum amount of code needed to draw sprites to the screen. Here's a small summary of what you'll find in the source files:

- `resources/display_config.ron`  
  Contains the window configuration (size, title).

- `src/main.rs`  
  Creates the render graph, adds the required bundles, builds the game data with our own state and finally, starts the game's main event loop.

- `src/state.rs`  
  Implements the main game state. In the `on_start` hook, the camera is initialized, and the sprites that will be drawn are loaded and their entities created.  
   In the `handle_event` hook, we print any keys that were pressed and close the window if the user presses escape or the OS requests that we quit.
