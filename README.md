# Property Tycoon

A digital, Monopoly-style board game built with **Godot 4.3** and **C#**. Players move around a board buying properties, paying rent, drawing cards, and trying to bankrupt their opponents.

## Features

- **Player selection screen** — choose the number of human and AI players (up to 6 total) and pick an avatar before each match
- **Full turn loop** — dice rolling, movement, passing Go, landing on properties, jail, and free parking, handled by a central game loop
- **Card system** — Pot Luck and Opportunity Knocks card decks with a card display UI
- **Jail mechanics** — pay bail, use a "Get Out of Jail Free" card, or wait out your turns
- **Settings menu** — separate volume sliders for master, music, SFX, and voice, plus window/resolution mode options
- **Developer console** — an in-game command prompt for debugging during development
- **Automated tests** — GdUnit4 test suite covering cards, the game loop, and the player selection screen

## Tech stack

- [Godot Engine 4.3](https://godotengine.org/) (.NET/C# build, Forward+ renderer)
- C# targeting .NET 8.0 (`net7.0` on Android)
- [gdUnit4](https://github.com/MikeSchulze/gdUnit4) for unit testing

## Project structure

```
Scenes/       # Godot scenes: main menu, player selection, game board, settings, audio
Scripts/      # C# game logic (GameLoop, Player, Card, menus, sliders, etc.)
Scripts/Tests/# gdUnit4 test scripts
Objects/      # Reusable scene objects (cards, jail bail, free parking, command line)
Assets/       # Board, card, dice, avatar, and player icon art
Audio/        # Music and sound assets
addons/       # Editor plugins (Git integration, To-Do Manager, gdUnit4)
```

## Getting started

### Prerequisites

- [Godot 4.3](https://godotengine.org/download) with .NET/C# support (the "Godot .NET" build, not the standard build)
- [.NET SDK 8.0](https://dotnet.microsoft.com/download) or later

### Running the game

1. Clone the repository:
   ```bash
   git clone <repo-url>
   cd property-tycoon
   ```
2. Open the project folder in Godot (it will detect `project.godot` automatically).
3. Let Godot build the C# solution on first open (or run `dotnet build` from the project root).
4. Press **Run** (F5) in the editor, or run the exported build directly. The game starts on the main menu (`Scenes/Main_Menu.tscn`).

### Running tests

Tests use gdUnit4 and live under `Scripts/Tests/`. With the gdUnit4 editor plugin enabled (it's included under `addons/`), you can run the suite from the Godot editor's test panel, or via the command line:

```bash
addons/gdUnit4/runtest.sh   # Linux/macOS
addons/gdUnit4/runtest.cmd  # Windows
```

## Controls

- **`** (backtick) — open the developer command prompt
- **Space** — dismiss the in-game menu

(Full input mappings are configurable in `project.godot` / the Godot Input Map.)

## License

MIT — see [LICENSE](LICENSE) for details.
