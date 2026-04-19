# PAVE - Public Address Voice Engine

A modern PA system management platform built for Vidya Valley School, Pune.

## What is PAVE?

PAVE replaces the traditional intercom-based PA system with a web-controlled announcement platform. Staff can log in from any device, record or upload announcements, and manage the PA system - without touching any hardware.

## Key Capabilities

- **Browser-Based Control**: Record or upload announcements directly from any device on the network
- **Scheduled Playback**: Set audio to play on specific days and times automatically
- **Role-Based Access**: Separate Admin and standard user permissions
- **Full Audit Log**: Every announcement is logged with uploader name, timestamp, and played status
- **Light & Dark Mode**: Adaptive UI for any environment

## Quick Start

1. Visit the dashboard hosted on GitHub Pages
2. Log in with your school credentials via Supabase Auth
3. Record or upload an announcement and hit play

## Architecture

```
[GitHub Pages - Frontend]
        |
        | Auth + DB queries
        v
[Supabase - Auth & Database]
        |
        | Pi polls for playback commands
        v
[Raspberry Pi Zero 2W - Audio Playback]
        |
        | 3.5mm aux
        v
[School PA System]
```

- The **frontend** is a static HTML/CSS/JS site hosted on **GitHub Pages** - no frameworks
- **Supabase** handles user authentication and stores the recording log
- The **Raspberry Pi Zero 2W** polls Supabase for playback commands and outputs audio via aux to the PA system

## Tech Stack

| Component | Technology |
|---|---|
| Frontend | HTML, CSS, JavaScript - hosted on GitHub Pages |
| Auth & Database | Supabase |
| Hardware | Raspberry Pi Zero 2W |
| Audio Output | 3.5mm aux to PA amplifier |
| Process Management | systemd |



## Future Scope

- **Bell automation** - Timed scheduling to control school bells automatically
- **Speaker zoning** - Independent control of different speaker zones across the school
- **OTA updates** - Push config or audio files to the Pi remotely

## Project Status

🚧 **In active development** - Core playback, recording log, scheduling, and role-based access are functional.

## About

PAVE is a student project developed at **Vidya Valley School, Pune**, modernising school infrastructure with affordable open-source hardware and software.
