# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with this repository.

## Project Overview

junit-xml-test-fixtures is a **reference collection** of JUnit/xUnit XML test fixtures, schemas, and format documentation aggregated from vendor and community projects.

## Purpose

Centralized collection of real-world JUnit XML examples to inform and validate the Jux JUnit XML parser implementation. This repository serves as:

- **Schema reference**: XSD definitions from multiple sources
- **Format documentation**: Links to official format specifications
- **Test fixtures**: Real XML examples from testing frameworks
- **Dialect catalog**: Documentation of JUnit XML variants

## Repository Structure

```
junit-xml-test-fixtures/
├── CLAUDE.md                      # This file
├── README.md                      # Comprehensive documentation
├── .gitmodules                    # Submodule definitions
│
├── # Schema Submodules
├── windyroad-junit-schema/        # Apache Ant JUnit XSD (Apache-2.0)
├── junit5/                        # Official JUnit 5 with Jenkins XSD (EPL-2.0)
│
├── # Testing Framework Submodules
├── pytest/                        # pytest JUnit XML generation (MIT)
├── python-polarion/               # Polarion ALM client (MIT)
│
├── # JavaScript/BDD Submodules
├── cucumber-junit-xml-formatter/  # Cucumber BDD formatter (MIT)
├── jest-junit/                    # Jest reporter (Apache-2.0)
└── karma-junit-reporter/          # Karma browser testing (MIT)
```

## Submodule Management

### Current Submodules (7)

All submodules use permissive licenses compatible with Apache-2.0:

| Submodule | License | Purpose |
|-----------|---------|---------|
| windyroad-junit-schema | Apache-2.0 | De facto standard JUnit XSD |
| junit5 | EPL-2.0 | Official JUnit 5 with Jenkins XSD |
| pytest | MIT | Python testing framework |
| python-polarion | MIT | Polarion ALM integration |
| cucumber-junit-xml-formatter | MIT | BDD test reporting |
| jest-junit | Apache-2.0 | JavaScript testing |
| karma-junit-reporter | MIT | Browser testing |

### Common Commands

```bash
# Clone with submodules
git clone <url> junit-xml-test-fixtures
cd junit-xml-test-fixtures
git submodule update --init --recursive

# Update all submodules
git submodule update --remote --merge

# Add a new submodule (check license first!)
git submodule add <url> <path>

# Remove a submodule
git submodule deinit -f <path>
git rm -f <path>
rm -rf .git/modules/<path>
```

## Schema References (External)

The README documents these external schema references (not submodules):

- **Maven Surefire XSD**: Official Apache Maven test report schema
- **xUnit.net XML Format v2**: .NET xUnit format specification
- **NUnit XML Format**: .NET NUnit 3.x format specification

## License Policy

**CRITICAL**: Only include submodules with permissive licenses (MIT, Apache-2.0, BSD, EPL).

**Do NOT add submodules with**:
- GPL/LGPL licenses (copyleft, incompatible with Apache-2.0)
- No license specified (all rights reserved by default)

**Removed submodules** (documented in README for reference only):
- dump2polarion, polarize, polarizer (GPL)
- testmoapp, jenkinsci-xunit-plugin (no license)

## Git Workflow

See `CLAUDE.local.md` for remote URLs (excluded from version control).

### Branch Strategy

- **main**: Stable releases, pushed to both remotes
- **develop**: Active development, primary remote only

## Related Projects

| Project | Relationship |
|---------|--------------|
| jux | Server that parses JUnit XML |
| pytest-jux | Client that generates signed JUnit XML |
| py-juxlib | Shared library with XML canonicalization |

## AI Development Guidelines

### When Adding Submodules

1. **Check license first** using GitHub API or repository inspection
2. **Only add permissive licenses** (MIT, Apache-2.0, BSD, EPL)
3. **Update README** with new submodule documentation
4. **Update License Notes** section in README
5. **Commit and push** to both remotes

### When Adding Schema References

1. **Verify URL accessibility**
2. **Document the format** with key elements
3. **Note the license** if known
4. **Add to Schema Definitions** section in README

### README Structure

The README follows a consistent pattern for each entry:
- **Repository/URL**: Source location
- **Path**: Local submodule path (if applicable)
- **Description**: Brief purpose
- **Maintained By**: Author/organization
- **License**: SPDX identifier
- **Key Files**: Important files to reference
- **Relevant Formats**: What formats this covers

## Maintenance Notes

- Submodules point to upstream repositories (not modified)
- README is the primary documentation
- License compliance is mandatory
- Keep documentation for removed submodules (historical reference)
