# Sozo

Sozo is a powerful migration planning tool designed to streamline the updating and deployment of AWs. It provides a robust binary command-line interface (CLI) that simplifies World management tasks, enabling you to focus on the creative aspects of World-building. Future versions will provide a GUI.

## Features

- **Binary CLI**: Sozo provides an intuitive binary CLI, ensuring easy management of your Worlds, whether you're updating existing ones or deploying new ones.

## Installation

The `sozo` binary can be installed via [`dojoup`](../../getting-started/installation.md), our dedicated installation package manager.

### Installing from Source

If you prefer to install from the source code:

```sh
cargo install --path ./crates/sozo  --force
```

This will install Sozo and the required dependencies on your local system.

## API

### Help

Show all options

```bash
sozo --help
```

### Initialize

Initialize a new project. This will build the starter example.

```bash
sozo --init
```

### Building

After you have designed your world you will then need to build it. This command compiles your contracts and injects the `commands`. After this the contracts are ready to deploy! 

```bash
sozo --build examples/
```

### Migrate

Once you built your contracts successfully you can then deploy them on a network! The following will deploy onto the local Katana network. Make sure you have it running. Check for instructions [here](../katana/overview.md)

```bash
sozo --migrate examples/
```

This command will prompt Sozo to build and deploy all Worlds found within the specified directory.

### Test

```bash
sozo --test examples/
```

### Execute

This will execute the world system

```bash
sozo execute --world <world> <system> <call_data>
```

---

### Component

The component API is nested within sozo and has its own set of commands. Use the component API to interact with components and systems within your world.

See all component options

```bash
sozo component --help
```

##### Get

Get class hash of Moves component by name

```bash
sozo component get --world <world> <component name>
```

##### Schema

Fetches schema of component

```bash
sozo component schema --world <world> <component name>
```

##### Entity

Fetches entity component within world.

```bash
sozo component entity --world <world> <component name> <entity>
```