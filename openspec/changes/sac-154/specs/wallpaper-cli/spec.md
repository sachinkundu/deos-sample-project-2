## Purpose

This capability gives users a simple command line flow with clear help, stable results, and tests they can trust.

## ADDED Requirements

### Requirement: Provide clear commands

The app SHALL provide `browse`, `fetch`, and `set` commands. Its help MUST state what each command does and list its inputs and options.

#### Scenario: Show main help

- **WHEN** a user asks for help with no command.
- **THEN** the app lists the three commands, gives a short use line for each one, and exits with a zero status.

#### Scenario: Show command help

- **WHEN** a user asks for help with one command.
- **THEN** the app lists the inputs and options for that command and exits with a zero status.

### Requirement: Use stable exit status

The app SHALL use a zero exit status for success and a nonzero exit status for failure. It SHALL give a clear error when a command fails.

#### Scenario: Command succeeds

- **WHEN** a command completes its requested action.
- **THEN** the app exits with a zero status.

#### Scenario: Input is not valid

- **WHEN** a user omits a needed input or gives an option that is not valid.
- **THEN** the app gives a clear error and exits with a nonzero status.

### Requirement: Cover key flows with tests

The project SHALL include automated tests for the main command flows and their common faults.

#### Scenario: Run the test suite

- **WHEN** a developer runs the test suite in a clean test setup.
- **THEN** the suite checks the main command flows and their common faults.
