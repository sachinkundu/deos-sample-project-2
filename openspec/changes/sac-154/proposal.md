## Why

Ubuntu GNOME users need a quick way to find a good wallpaper and use it at once. A small command line app can make this task clear, fast, and easy to trust.

## What Changes

- Add `browse` and `fetch` commands for Bing and Unsplash, plus a `set` command for the desktop.
- Show each choice with its source and a key that a user can use to fetch it.
- Save a fetched image to a local path chosen by the user and report that path.
- Check that a local file is an image, then set it as the Ubuntu GNOME background.
- Give clear help and useful errors, with zero for success and a nonzero exit status for failure.
- Add tests for the main flows and their common faults.

## Capabilities

### New Capabilities

- `wallpaper-catalog`: Browse and fetch wallpaper images from Bing and Unsplash.
- `gnome-background`: Check and set a local image as the Ubuntu GNOME background.
- `wallpaper-cli`: Give users a clear command line flow, useful errors, and test coverage.

### Modified Capabilities

None.

## Impact

The change adds a new command line app, calls to Bing and Unsplash, local image files, and Ubuntu GNOME desktop settings. It also adds user help and automated tests. No current command or file format will change.
