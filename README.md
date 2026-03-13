# BITS — Private Ledger

A privacy-first cryptocurrency built for resilient mesh networks.

## What is BITS

BITS is a fork of Wownero (Monero-derived) modified for operation
on low-bandwidth mesh networks using Reticulum over LoRa and WiFi.

Designed to function indefinitely without internet connectivity,
grid power, or centralised infrastructure.

## Key Parameters

| Parameter | Value | Notes |
|---|---|---|
| Block Reward | Fixed 9 BITS | No halving, no supply cap, perpetual |
| Block Time | 400 seconds | LoRa propagation margin |
| Difficulty Algorithm | LWMA-40 | Rapid response to node loss |
| Proof of Work | RandomWOW | CPU-friendly, ASIC resistant |
| Privacy | RingCT + Stealth Addresses | Inherited from Monero |
| Max Block Size | 529 KB | 23 squared KB where 23 is the 9th prime |
| P2P Port | 14400 | |
| Max Peers | 9 | 4 outbound + 5 inbound |
| Genesis Message | Welcome to File City | |

## Pythagorean Architecture

BITS consensus parameters are bound by the (9, 40, 41) Pythagorean triple:

9 squared + 40 squared = 41 squared

| Value | Role |
|---|---|
| 9 | Block reward in BITS |
| 40 | LWMA difficulty window |
| 41 | Difficulty observation window and damping factor |
| 400 | Block time in seconds (40 x 10) |

## Network Transport

BITS nodes communicate over Reticulum, a cryptographic transport
layer that operates over LoRa, WiFi, or any available medium.
All traffic is encrypted and authenticated by default.

Tested and confirmed operational over Heltec ESP32 LoRa V3
devices on the 915MHz AU ISM band.

## Current Status

- Testnet: Active
- LoRa mesh: Confirmed operational
- Transactions over LoRa: Confirmed
- Mainnet: Pending

## Building From Source

### Dependencies (Debian / Ubuntu / Pop OS)

sudo apt update
sudo apt install -y build-essential cmake pkg-config libboost-all-dev libssl-dev libzmq3-dev libunbound-dev libsodium-dev libreadline-dev libexpat1-dev libpgm-dev libhidapi-dev libusb-1.0-0-dev libprotobuf-dev protobuf-compiler libudev-dev git

### Build

git clone https://github.com/Noahthearkbuilder/bits.git
cd bits
mkdir build && cd build
cmake -D CMAKE_BUILD_TYPE=Release -D ARCH=x86-64 ..
make -j$(nproc)

## Philosophy

No kings. No supply cap games. No halving cliffs.
Every generation mines at the same rate for a millennium.
The mesh is the bank. Truth is the ledger.

## License

See LICENSE file. Derived from Wownero/Monero (BSD-3-Clause).
