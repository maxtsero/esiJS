# Change Log
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]
<!-- #### Added -->
<!-- #### Changed -->
<!-- #### Removed -->

## Major Releases:
### v0.1.0 - 2019 06 29
- Initial Release

### [v2.0.0] - 2019 07 03
#### Added
- All non-SSO ESI endpoints
- Docs
- `getSettings` and `setSettings`
#### Changed
- Updated README.md
- Improved error handling
- Changed constants declared as `let`s to `const`s
- Datasource is now modifiable

### [v3.0.0] - 2019 08 24
#### Added
- JSDoc
- `inputValidation` and `request` (#4, #5)
#### Changed
- Codebase Refactoring (@JFCodes, #4, @cppctamber, #5)
- `endpoints.js`
#### Removed
- `addArrays`

## Minor Releases:
### [v1.0.1] - 2019 06 29
#### Added
- CHANGELOG.md
- Mocha/Chai testing
#### Changed
- Package.json to support Mocha tests

### [v2.1.0] - 2019 07 12
#### Added
- `addArrays` and `sleep`
#### Changed
- Errors are now thrown instead of returned
- Changed the name of `alliances.icons` to `alliances.icon`

### [v2.1.2] - 2019 07 12
#### Added
- Nothing
#### Changed
- `Lodash` security fix
### [v3.0.2] - 2019 08 24
#### Changed
- Fixed some bugs with the refactoring

<!-- LINKS -->
<!-- RELEASES -->
[Unreleased]: https://github.com/GingkathFox/EveJS/compare/v0.1.1...dev
[v0.1.1]: https://github.com/GingkathFox/EveJS/compare/v0.1.0...v0.1.1
<!-- ISSUES -->
