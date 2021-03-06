# Changelog

## [Unreleased]

### Fixed

- `RRule::offsetGet` and `RSet::offsetGet` throw `InvalidArgumentException` for illegal offset types [#22](https://github.com/rlanvin/php-rrule/issues/22)
- Update exception message for UNTIL parse error [#23](https://github.com/rlanvin/php-rrule/pull/23)

## [1.4.0] - 2016-11-11

### Added

- Add `RRule::getRule()` method to return original rule array [#17](https://github.com/rlanvin/php-rrule/pull/17)
- Add `RSet::getRRules()`, `RSet::getExRules()`, `RSet::getDates()` and `RSet::getExDates()`
- Tests for PHP 7.0

### Fixed

- Fix a bug in `rfcString` when using a frequency constant (instead of a string) to create the rule [#16](https://github.com/rlanvin/php-rrule/pull/16)
- Fix a undefined index bug in RFC parser

## [1.3.1] - 2016-08-09

### Added

- Italian translation (it) [#14](https://github.com/rlanvin/php-rrule/pull/14)

### Fixed

- Fixed a bug when combining values with an integer modifier and regular values in `BYDAY` (example `1MO,FR`)
- Fixed RRule created with a timestamp start date generates an invalid RFC string [#15](https://github.com/rlanvin/php-rrule/issues/15)

## [1.3.0] - 2016-07-08

### Added

- Spanish translation (es) [#12](https://github.com/rlanvin/php-rrule/pull/12)
- `$include_timezone` parameter to `RRule::rfcString()` to produce a RFC string without timezone information

### Fixed

- `RRule::parseRfcString()` is strictier and will not accept invalid `DTSTART` and `UNTIL` formats (use the array syntax in the constructor with `DateTime` objects if you need to create rules with complex combinations of timezones). [#13](https://github.com/rlanvin/php-rrule/issues/13)

## [1.2.0] - 2016-04-09

### Added

- Support for fallback locale when using `RRule::humanReadable()` [#11](https://github.com/rlanvin/php-rrule/pull/11)
- Dutch translation (nl) [#9](https://github.com/rlanvin/php-rrule/pull/9)

### Fixed

- Fixed fatal error Locale class not found when intl extension is not loaded [#10](https://github.com/rlanvin/php-rrule/issues/10)

## [1.1.0] - 2016-03-30

### Added

- New class `RRule\RSet` (recurrence set) that can combine multiple RRULE, EXRULE, RDATE and EXDATE. [#7](https://github.com/rlanvin/php-rrule/issues/7)
- New interface `RRule\RRuleInterface` to unify `RRule` and `RSet`
- New methods: `isFinite()`, `isInfinite()`

### Fixed

- Fix bug preventing the iteration of multiple instances of RRule at the same time
- Fix `occursAt` failing when the date passed was a different timezone [#8](https://github.com/rlanvin/php-rrule/pull/8)
- Fix bug at WEEKLY frequency with a partially filled cache in some circumstances
- Fix various reference bugs causing corruption of the cache in some circumstances (related to DateTime object being mutable)

### Removed

- The alias `RRule::occursOn` has been removed (use `occursAt` instead)

## [1.0.1] - 2016-03-11

### Fixed

- Ensure the results are returned in the same timezone as DTSTART. [#6](https://github.com/rlanvin/php-rrule/issues/6)
- LogicException namespacing bug. [#3](https://github.com/rlanvin/php-rrule/issues/3)

## 1.0.0 - 2016-03-02

### Added

- First release, everything before that was unversioned (`dev-master` was used).

[Unreleased]: https://github.com/rlanvin/php-rrule/compare/v1.4.0...HEAD
[1.4.0]: https://github.com/rlanvin/php-rrule/compare/v1.3.1...v1.4.0
[1.3.1]: https://github.com/rlanvin/php-rrule/compare/v1.3.0...v1.3.1
[1.3.0]: https://github.com/rlanvin/php-rrule/compare/v1.2.0...v1.3.0
[1.2.0]: https://github.com/rlanvin/php-rrule/compare/v1.1.0...v1.2.0
[1.1.0]: https://github.com/rlanvin/php-rrule/compare/v1.0.1...v1.1.0
[1.0.1]: https://github.com/rlanvin/php-rrule/compare/v1.0.0...v1.0.1
