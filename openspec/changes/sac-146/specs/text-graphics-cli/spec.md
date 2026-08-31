## Purpose

This capability lets a person create common text art by naming a graphic in a terminal command.

## ADDED Requirements

### Requirement: Generate a supported graphic

The tool SHALL accept `text-graphics generate <request>`. It SHALL ignore letter case and spaces at the start or end of the request. It SHALL support the names `heart`, `star`, `smiley`, and `diamond`.

#### Scenario: Generate a graphic by name

- **WHEN** a person runs `text-graphics generate heart`.
- **THEN** the tool writes a heart made from text characters to standard output.
- **AND** the tool exits with status 0.

#### Scenario: Normalize a graphic name

- **WHEN** a person requests a supported graphic with different letter case or spaces at the start or end.
- **THEN** the tool writes the same graphic as it does for the normalized name.
- **AND** the tool exits with status 0.

### Requirement: Keep graphic output terminal friendly

Each supported graphic SHALL use plain text characters, spaces, and line breaks only. No output line SHALL be more than 80 characters wide. A successful run SHALL write only the graphic to standard output.

#### Scenario: Show a graphic in a plain terminal

- **WHEN** the tool makes any supported graphic.
- **THEN** each output line is no more than 80 characters wide.
- **AND** the output has no color or cursor control codes.
- **AND** standard output has no label or status message outside the graphic.

### Requirement: Reject an unsupported request

The tool SHALL reject a graphic name that is not in its supported list. It SHALL write an error to standard error, name the unsupported request, and tell the person to run help. It SHALL not write a graphic to standard output.

#### Scenario: Request an unknown graphic

- **WHEN** a person runs `text-graphics generate moon`.
- **THEN** the tool writes an error to standard error that names `moon`.
- **AND** the error tells the person how to view help.
- **AND** the tool writes nothing to standard output.
- **AND** the tool exits with a non-zero status.

### Requirement: Reject a missing request

The tool SHALL reject the generate command when it has no graphic request. It SHALL write a short usage hint to standard error and SHALL not write a graphic to standard output.

#### Scenario: Run generate without a request

- **WHEN** a person runs `text-graphics generate` with no request.
- **THEN** the tool writes a usage hint to standard error.
- **AND** the tool writes nothing to standard output.
- **AND** the tool exits with a non-zero status.

### Requirement: Explain available commands

The tool SHALL show help for `text-graphics help` and `text-graphics --help`. Help SHALL include the generate command syntax, every supported graphic name, and at least one full example. A help request SHALL exit with status 0.

#### Scenario: View help

- **WHEN** a person runs `text-graphics --help`.
- **THEN** the output shows how to use the generate command.
- **AND** the output lists `heart`, `star`, `smiley`, and `diamond`.
- **AND** the output shows a full generate example.
- **AND** the tool exits with status 0.

#### Scenario: Use the help command

- **WHEN** a person runs `text-graphics help`.
- **THEN** the tool shows the same help content as `text-graphics --help`.
- **AND** the tool exits with status 0.
