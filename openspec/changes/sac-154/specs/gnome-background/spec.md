## Purpose

This capability checks a local image and sets it as the visible background for an Ubuntu GNOME desktop session.

## ADDED Requirements

### Requirement: Set the desktop background

The app SHALL set a valid local image as the background in the current Ubuntu GNOME session.

#### Scenario: Set a valid image

- **WHEN** a user asks the app to set a local image that can be read.
- **THEN** the app sets that image for the current desktop and exits with a zero status.

### Requirement: Check the image before a change

The app SHALL reject a local path when it is missing or does not hold an image.

#### Scenario: Image is missing

- **WHEN** the user gives a path that does not point to a file.
- **THEN** the app reports that the image is missing and exits with a nonzero status.

#### Scenario: File is not an image

- **WHEN** the user gives a file that is not a valid image.
- **THEN** the app reports that the file is not an image and exits with a nonzero status.

### Requirement: Reject an unsupported desktop

The app SHALL give a clear error when it cannot change the background in the current Ubuntu GNOME session.

#### Scenario: GNOME session is not active

- **WHEN** a user asks to set an image outside a supported Ubuntu GNOME session.
- **THEN** the app gives a clear support error and exits with a nonzero status.

#### Scenario: Desktop setting fails

- **WHEN** the desktop rejects the new background setting.
- **THEN** the app reports the failed change and exits with a nonzero status.
