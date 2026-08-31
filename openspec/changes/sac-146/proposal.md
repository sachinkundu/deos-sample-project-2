## Why

People need a fast way to make familiar text art in a terminal. A small command can save them from drawing each shape by hand.

## What Changes

- Add `text-graphics generate <request>`. It trims spaces at each end, ignores letter case, prints the graphic to standard output, and exits with status 0.
- Include built-in `heart`, `star`, `smiley`, and `diamond` graphics.
- For a missing or unsupported request, write a clear error to standard error, write no graphic to standard output, and exit with a non-zero status. Name an unsupported request and point to help. For a missing request, show a short usage hint.
- Show the same help for `text-graphics help` and `text-graphics --help`. Both forms exit with status 0 and list the generate syntax, every supported name, and a full example.
- Use only plain text characters, spaces, and line breaks in each graphic. Keep each line at 80 characters or less. On success, write only the graphic to standard output, with no color or cursor control codes.

## Capabilities

### New Capabilities

- `text-graphics-cli`: Generate built-in text graphics and explain their use from a command-line tool.

### Modified Capabilities

None.

## Impact

The change adds a command-line entry point, a small built-in graphic catalog, input checks, and help text. It does not need a network service or stored user data.
