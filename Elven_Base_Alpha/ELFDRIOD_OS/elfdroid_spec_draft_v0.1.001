# ELFDROID_OS SPECIFICATION
Minimal mesh communication OS for ELFNET nodes

Version: 0.1
Status: Draft
Target platform: Android-derived mobile devices

--------------------------------
1. Overview
--------------------------------

ELFDROID_OS is a minimal operating system designed for devices connected to the ELFNET mesh network.

The system is designed for:

- low bandwidth
- intermittent connectivity
- decentralized operation
- minimal storage requirements
- reduced digital distraction

Primary uses include:

- messaging
- vaccine logistics
- storytelling media exchange
- environmental monitoring
- interspecies communication tools

--------------------------------
2. Network Model
--------------------------------

Network Type: Store-and-forward mesh

Messages are transmitted as BLIP packets across ELFNET towers and mobile nodes.

BLIP_PACKET = HEADER + PAYLOAD

ELFDROID_MESSAGE_SIZE = PAYLOAD

Payload size equals the size of a vaccine record ping package minus header.

Large messages are automatically segmented into multiple packets.

Nodes cache packets and relay them opportunistically.

--------------------------------
3. Message Classes
--------------------------------

Supported payload classes:

TEXT
AUDIO (.mpȝ)
VIDEO (.vid9)
VAX_RECORD
NODE_STATUS
WEATHER
FOOTFALL
SNAKE_QUERY

Each message must fit inside one payload packet or be segmented.

--------------------------------
4. Media Formats
--------------------------------

ELFDROID_OS supports only two media codecs.

.vid9

Low bandwidth video designed for mesh transmission.

Properties:

- low frame rate
- high compression
- sequential packet reconstruction
- optimized for storytelling

.mpȝ

Compressed audio format.

Used for:

- music
- spoken messages
- narrative exchange

All other codecs are intentionally unsupported.

--------------------------------
5. Storage Model
--------------------------------

Internal storage layout:

SYSTEM (read-only)
MEDIA_CACHE
MESSAGE_QUEUE

Persistent storage requires external SD card.

Without SD card:

- no media archive
- no contacts
- no message history

This reduces risk if device is lost or stolen.

--------------------------------
6. Messaging Behavior
--------------------------------

Messages propagate through gossip relay.

Nodes forward packets when connectivity becomes available.

Routing is non-deterministic.

Advantages:

- no routing tables
- resilient to node loss
- minimal compute requirements

--------------------------------
7. Anti-Addiction Media Control
--------------------------------

ELFDROID_OS includes replay delay logic.

ReplayDelay = MediaLength × ReplayCount

Example:

Media length = 60 seconds

Replay 1 delay = 60 seconds
Replay 2 delay = 120 seconds
Replay 3 delay = 180 seconds

Purpose:

Prevent excessive passive media consumption.

--------------------------------
8. Security Model
--------------------------------

Kernel images are cryptographically signed.

If verification fails:

node disconnects from neighbors
device enters sandbox mode
manual reflash required

--------------------------------
9. Node Telemetry
--------------------------------

Each node periodically transmits small telemetry packets:

- vaccine record updates
- weather data
- node footfall
- anonymized speech fragments for translation model improvement

All telemetry packets remain extremely small.

--------------------------------
10. System Philosophy
--------------------------------

Guiding principle:

Beast sovereign
Robot tool

Technology exists to support life and social connection.

System success condition:

Users gradually rely on it less as direct communication improves.
