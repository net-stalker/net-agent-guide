# Developer Guide for net-agent

## Overview

`net-agent` is a Rust-based CLI application designed for capturing network traffic, which can be further analyzed using the Net Stalker project. The application leverages the `pcap` crate for packet capturing and aims to provide a simple yet extensible platform for network traffic analysis.

## Project Structures

- **src/**: Contains the main source code.
- **Cargo.toml**: Project metadata and dependencies.
- **README.md**: User guide and basic information.

## Key Concepts

### Packet Capturing

The core functionality of `net-agent` revolves around capturing network packets using the `pcap` crate. This is achieved by interfacing directly with network devices and recording traffic data.

### Configuration Management

Configurations can be provided via command-line options or a configuration file in TOML format. This flexibility allows users to customize their capturing setup easily.

### Output Handling

Captured traffic is stored in the specified output directory, making it accessible for subsequent analysis.

## Setting Up Development Environment

To contribute to `net-agent`, follow these steps:

1. **Clone the Repository**

2. **Install Dependencies:**

    Ensure you have Rust and Cargo installed. Install necessary dependencies:

    ### Linux

    - Ubuntu/Debian:

        ```shell
        sudo apt-get install libpcap-dev
        ```

    - Fedora:

        ```shell
        sudo dnf install libpcap-devel
        ```

    - Arch:

        ```shell
        sudo pacman -S libpcap
        ```

    ### macOS

    - `libpcap` should be installed on Mac OS X by default.

    ### Windows

    1. Install [Npcap](https://npcap.com/#download).

    2. Download the [Npcap SDK](https://npcap.com/#download).

    3. Add the SDK's `/Lib` or `/Lib/x64` folder to your `LIB` environment variable.

## Development Practices

### Code Style

- Follow the Rust coding guidelines.
- Use `rustfmt` for code formatting and `clippy` for linting.

### Testing

- Write unit tests for individual functions.
- Create integration tests for end-to-end functionality.

### Documentation

- Use `///` doc comments for public functions and modules.
- Provide examples where applicable.
- Keep the `README.md` and user guide updated with new features.

## Extending Functionality

### Adding Traffic Filtering

To implement runtime traffic filtering (e.g., capturing packets of a specific protocol), follow these steps:


1. **Modify Capture Logic:**

    Update the packet capture logic to include filtering. It would be much better to include network packets filtering at runtime to get only specific converstations.

2. **Add CLI Option:**

    Extend the CLI to accept protocol filters.

### Enhancing Data Handling with Channels

For better handling of captured data, consider using sockets to send captured packets to another process or system for concurrent processing. It would be preferable to make `net-agent` work with multiple protocols like `UDP`, `TCP` or `QUIN`. 

### Potential Enhancements

- **Protocol Decoding:** Implement detailed decoding for various protocols using crates like `pnet`.
- **Performance Optimization:** Profile and optimize packet capturing and processing.
- **Extensive Filtering:** Support more sophisticated filters (e.g., BPF syntax).
- **GUI Integration:** Consider adding a graphical interface for easier configuration and usage.

## Contributing

1. Clone the repository and create a new branch for your feature or bugfix.
2. Ensure your code is well-tested and documented.
3. Submit a pull request to `develop` branch with a clear description of your changes.

For any questions or further guidance, refer to the project's [issue tracker](https://github.com/net-stalker/net-agent/issues) or contact the maintainers.
