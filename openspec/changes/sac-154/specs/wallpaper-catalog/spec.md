## Purpose

This capability lets users view wallpaper choices from Bing and Unsplash and save a chosen image on their computer.

## ADDED Requirements

### Requirement: Browse wallpaper choices

The app SHALL let a user browse wallpaper choices from Bing or Unsplash. Each choice MUST show its source and a key that can be used to fetch it.

#### Scenario: Browse Bing choices

- **WHEN** a user asks to browse Bing.
- **THEN** the app lists Bing choices with a source and fetch key for each choice.

#### Scenario: Browse Unsplash choices

- **WHEN** a user asks to browse Unsplash.
- **THEN** the app lists Unsplash choices with a source and fetch key for each choice.

### Requirement: Fetch a chosen wallpaper

The app SHALL fetch a choice by its source and key. It SHALL save the image at the path chosen by the user and report that path.

#### Scenario: Fetch succeeds

- **WHEN** a user gives a valid source, fetch key, and output path.
- **THEN** the app saves the image at that path and reports the saved path.

### Requirement: Report source faults

The app SHALL give a clear error when Bing or Unsplash cannot serve a browse or fetch request.

#### Scenario: Source cannot be reached

- **WHEN** the app cannot reach the chosen source.
- **THEN** it reports the fault and exits with a nonzero status.
