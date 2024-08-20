# Introduction

[![Crates.io](https://img.shields.io/crates/v/net-agent.svg)](https://crates.io/crates/net-agent)
[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

## What is net-agent?

**Net-Agent** is a command-line utility under the **Netstalker** project designed for network traffic capture. This tool allows you to capture network traffic on your machine, which can then be uploaded to your personal cabinet for analysis.

## Features

- **Network Traffic Capture**: Capture all network packets on your machine.
- **Independent Packet Storage**: Each packet is stored in a separate file for easier management and analysis.
- **Cross-Platform Compatibility**: Works on any operating system.

## How It Works

Net-Agent leverages the [pcap crate](https://crates.io/crates/pcap) for capturing network packets. The captured packets are saved in the directory of your choice.

## Future Enhancements

We plan to introduce the following features to enhance the usability of Net-Agent:

- **Traffic Filtering by Protocol**: Filter captured traffic by protocols to focus on specific types of network data.
- **Enhanced Management Tools**: Additional tools to help users manage and analyze their captured traffic more conveniently.

---