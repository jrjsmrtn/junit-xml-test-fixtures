# JUnit XML Test Fixtures Repository

This repository aggregates vendor and community projects containing JUnit XML test fixtures and examples for various testing frameworks and tools.

## Purpose

Centralized collection of real-world JUnit XML examples to inform and validate the Jux JUnit XML parser implementation.

## Submodules

### pytest (Official)

**Repository**: https://github.com/pytest-dev/pytest
**Path**: `pytest/`
**Description**: Official pytest repository containing comprehensive JUnit XML generation tests
**Key Files**:
- `testing/test_junitxml.py` - Extensive test suite with xunit1 and xunit2 examples
- `src/_pytest/junitxml.py` - JUnit XML generation implementation

**Relevant Formats**:
- pytest xunit1 (legacy format with `junit_family=xunit1`)
- pytest xunit2 (modern format with `junit_family=xunit2`)

### dump2polarion (Community)

**Repository**: https://github.com/mkoura/dump2polarion
**Path**: `dump2polarion/`
**Description**: Python tool for generating Polarion-compatible xUnit XML
**Maintained By**: Martin Kourim
**Key Features**:
- Polarion modified xUnit format examples
- Test result transformation utilities
- Property mapping for Polarion ALM integration

**Relevant Formats**:
- Polarion modified xUnit with custom properties
- Requirements traceability examples

### polarize (Community - Java)

**Repository**: https://github.com/RedHatQE/polarize
**Path**: `polarize/`
**Description**: Java library for generating Polarion-compatible test metadata
**Maintained By**: Red Hat QE
**Key Features**:
- Java annotation-based Polarion integration
- xUnit XML generation with Polarion properties
- TestNG integration examples

**Relevant Formats**:
- Polarion modified xUnit from Java/TestNG
- Custom property mappings

### polarizer (Community - Java)

**Repository**: https://github.com/RedHatQE/polarizer
**Path**: `polarizer/`
**Description**: Another Red Hat project for Polarion test automation
**Maintained By**: Red Hat QE
**Key Features**:
- Polarion xUnit XML export
- Test case metadata management
- CI/CD integration patterns

**Relevant Formats**:
- Polarion modified xUnit with CI/CD metadata
- Test run configuration examples

## Usage

### Initial Clone

```bash
git clone <repository-url> junit-xml-test-fixtures
cd junit-xml-test-fixtures
git submodule update --init --recursive
```

### Update Submodules

```bash
git submodule update --remote --merge
```

### Finding Examples

#### pytest xunit1/xunit2 Examples

```bash
# View pytest JUnit XML tests
cat pytest/testing/test_junitxml.py

# View pytest JUnit XML implementation
cat pytest/src/_pytest/junitxml.py
```

#### Polarion Examples

```bash
# Python examples
ls dump2polarion/tests/
cat dump2polarion/dump2polarion/exporter.py

# Java examples
ls polarize/src/
cat polarize/README.md

# Alternative Java implementation
ls polarizer/src/
```

## Contributing Patterns to Jux

When adding new test fixtures to Jux based on these examples:

1. Extract minimal representative examples
2. Document the source project and version
3. Add XML comments explaining format-specific features
4. Place in appropriate `test/fixtures/junit_xml/` subdirectories:
   - `pytest/` for pytest examples
   - `polarion/` for Polarion examples

## License Notes

Each submodule has its own license. Please review individual project licenses before using examples:

- **pytest**: MIT License
- **dump2polarion**: GPL-2.0 License
- **polarize**: Apache License 2.0
- **polarizer**: Apache License 2.0

When extracting examples for Jux test fixtures, ensure compliance with source project licenses.

## Maintenance

This repository is maintained as part of the Jux project for reference purposes only. The submodules are not modified - they serve as upstream references for JUnit XML format validation.

**Last Updated**: 2025-10-25
**Maintainer**: Jux project team
