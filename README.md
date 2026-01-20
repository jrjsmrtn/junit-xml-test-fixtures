# JUnit XML Test Fixtures Repository

This repository aggregates vendor and community projects containing JUnit XML test fixtures and examples for various testing frameworks and tools.

## Purpose

Centralized collection of real-world JUnit XML examples to inform and validate the Jux JUnit XML parser implementation.

## Submodules

### Schema Definitions

#### windyroad/JUnit-Schema (Apache Ant XSD)

**Repository**: https://github.com/windyroad/JUnit-Schema
**Path**: `windyroad-junit-schema/`
**Description**: Most widely referenced XSD for Apache Ant's JUnit output format
**Maintained By**: Tom Howard (windyroad)
**Key Files**:
- `JUnit.xsd` - XML Schema Definition for JUnit XML format
- `jenkins-junit.xsd` - Jenkins-compatible variant

**Relevant Formats**:
- Apache Ant JUnit XML format (de facto standard)
- Used by junitparser and many validation tools

#### jenkinsci/xunit-plugin (Jenkins XSD)

**Repository**: https://github.com/jenkinsci/xunit-plugin
**Path**: `jenkinsci-xunit-plugin/`
**Description**: Jenkins xUnit plugin with multiple JUnit XSD versions
**Maintained By**: Jenkins CI community
**Key Files**:
- `src/main/resources/org/jenkinsci/plugins/xunit/types/model/xsd/junit-10.xsd` - Latest schema
- `src/main/resources/org/jenkinsci/plugins/xunit/types/model/xsd/junit-*.xsd` - Historical versions

**Relevant Formats**:
- Jenkins JUnit XML format (widely used in CI/CD)
- Multiple schema versions for backward compatibility
- Supports Ant JUnit and Maven Surefire formats

#### junit5 (Official JUnit 5)

**Repository**: https://github.com/junit-team/junit5
**Path**: `junit5/`
**Description**: Official JUnit 5 repository with Jenkins-compatible XSD
**Maintained By**: JUnit team
**Key Files**:
- `platform-tests/src/test/resources/jenkins-junit.xsd` - XSD used in JUnit 5 tests

**Relevant Formats**:
- Jenkins JUnit XML format (MIT License)
- Reference implementation from official JUnit team

### Testing Framework Implementations

#### pytest (Official)

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

### testmoapp (Reference Documentation)

**Repository**: https://github.com/testmoapp/junitxml
**Path**: `testmoapp/`
**Description**: JUnit XML file format reference guide and examples
**Maintained By**: Testmo (testmoapp)
**Key Features**:
- Comprehensive JUnit XML format documentation
- De facto standard format conventions
- Multiple example files covering common use cases
- Format specification and best practices

**Key Files**:
- `examples/junit-basic.xml` - Basic JUnit XML structure
- `examples/junit-complete.xml` - Complete example with all elements
- `examples/testcase-properties.xml` - Test case properties
- `examples/testcase-output.xml` - System output capture
- `examples/conventions.xml` - Common conventions and patterns

**Relevant Formats**:
- Standard JUnit XML format baseline
- Common conventions across testing tools
- CI/CD integration patterns

### JavaScript/BDD Frameworks

#### cucumber/junit-xml-formatter (BDD Testing)

**Repository**: https://github.com/cucumber/junit-xml-formatter
**Path**: `cucumber-junit-xml-formatter/`
**Description**: Cucumber JUnit XML formatter for reporting BDD test results
**Maintained By**: Cucumber community
**Key Files**:
- `jenkins-junit.xsd` - Jenkins-compatible JUnit XSD
- Cucumber Gherkin to JUnit XML transformation

**Relevant Formats**:
- BDD/Gherkin scenarios as JUnit XML
- Jenkins-compatible format

#### jest-community/jest-junit (JavaScript Testing)

**Repository**: https://github.com/jest-community/jest-junit
**Path**: `jest-junit/`
**Description**: Jest reporter creating compatible JUnit XML files
**Maintained By**: Jest community
**Key Files**:
- `__tests__/lib/junit.xsd` - JUnit XSD for validation
- Jest test results to JUnit XML transformation

**Relevant Formats**:
- JavaScript/Node.js test framework output
- Jenkins CI dtkit format

#### karma-runner/karma-junit-reporter (Browser Testing)

**Repository**: https://github.com/karma-runner/karma-junit-reporter
**Path**: `karma-junit-reporter/`
**Description**: Karma plugin for JUnit XML reporting
**Maintained By**: Karma community
**Key Files**:
- `junit-schema.xsd` - JUnit schema definition
- Browser test runner JUnit XML output

**Relevant Formats**:
- Browser-based JavaScript testing
- Karma test runner format

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

#### Schema Definitions

```bash
# windyroad Apache Ant XSD
cat windyroad-junit-schema/JUnit.xsd

# Jenkins xUnit plugin XSDs
ls jenkinsci-xunit-plugin/src/main/resources/org/jenkinsci/plugins/xunit/types/model/xsd/
cat jenkinsci-xunit-plugin/src/main/resources/org/jenkinsci/plugins/xunit/types/model/xsd/junit-10.xsd

# JUnit 5 official Jenkins-compatible XSD
cat junit5/platform-tests/src/test/resources/jenkins-junit.xsd
```

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

#### Testmoapp Reference Examples

```bash
# View all example files
ls testmoapp/examples/

# Basic JUnit XML structure
cat testmoapp/examples/junit-basic.xml

# Complete example with all elements
cat testmoapp/examples/junit-complete.xml

# Test case properties
cat testmoapp/examples/testcase-properties.xml

# System output capture
cat testmoapp/examples/testcase-output.xml

# Common conventions
cat testmoapp/examples/conventions.xml

# Read comprehensive format documentation
cat testmoapp/README.md
```

#### JavaScript/BDD Framework Examples

```bash
# Cucumber BDD JUnit XML
cat cucumber-junit-xml-formatter/jenkins-junit.xsd
ls cucumber-junit-xml-formatter/test/

# Jest JavaScript testing
cat jest-junit/__tests__/lib/junit.xsd
ls jest-junit/__tests__/

# Karma browser testing
cat karma-junit-reporter/junit-schema.xsd
ls karma-junit-reporter/test/
```

## Contributing Patterns to Jux

When adding new test fixtures to Jux based on these examples:

1. Extract minimal representative examples
2. Document the source project and version
3. Add XML comments explaining format-specific features
4. Place in appropriate `test/fixtures/junit_xml/` subdirectories:
   - `pytest/` for pytest examples
   - `polarion/` for Polarion examples
   - `testmoapp/` for reference format examples

## License Notes

Each submodule has its own license. All included submodules use permissive licenses compatible with Apache-2.0:

**Schema Definitions**:
- **windyroad-junit-schema**: Apache License 2.0
- **junit5**: Eclipse Public License 2.0

**Testing Frameworks**:
- **pytest**: MIT License

**JavaScript/BDD Frameworks**:
- **cucumber-junit-xml-formatter**: MIT License
- **jest-junit**: Apache License 2.0
- **karma-junit-reporter**: MIT License

**Removed Submodules** (documentation retained for reference):
- **dump2polarion**: Removed (GPL-2.0 - copyleft, incompatible with Apache-2.0)
- **polarize**: Removed (GPL-3.0 - copyleft, incompatible with Apache-2.0)
- **polarizer**: Removed (GPL-3.0 - copyleft, incompatible with Apache-2.0)
- **testmoapp**: Removed (no license specified - all rights reserved)
- **jenkinsci-xunit-plugin**: Removed (no license specified - all rights reserved)

When extracting examples for Jux test fixtures, ensure compliance with source project licenses.

## Maintenance

This repository is maintained as part of the Jux project for reference purposes only. The submodules are not modified - they serve as upstream references for JUnit XML format validation.

**Last Updated**: 2026-01-20
**Maintainer**: Jux project team
