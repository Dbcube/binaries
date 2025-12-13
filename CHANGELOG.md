# Changelog

All notable changes to Dbcube binaries will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [3.2.1] - 2025-12-10

### Query Engine
#### Fixed
- Fixed timestamp/datetime conversion returning null in MySQL
- Fixed timestamp/datetime conversion returning null in PostgreSQL
- Added proper chrono::NaiveDateTime and DateTime<Utc> handling

#### Changed
- Timestamps now returned in ISO format: `YYYY-MM-DD HH:MM:SS`
- UTC timestamps returned in RFC3339 format

### Schema Engine
#### Improved
- Better error messages for migration conflicts
- Enhanced foreign key constraint validation

### SQLite Engine
#### Optimized
- Performance improvements for large result sets
- Reduced memory footprint in long-running queries

---

## [3.2.0] - 2025-12-05

### Query Engine
#### Added
- Support for complex aggregations with GROUP BY
- Window functions support for PostgreSQL
- Enhanced JSON operations

### Schema Engine
#### Added
- Support for composite foreign keys
- Cascade delete/update options
- Auto-migration detection

### SQLite Engine
#### Added
- Native JSON1 extension support
- Full-text search (FTS5) integration

---

## [3.1.1] - 2025-11-20

### Query Engine
#### Fixed
- Connection pool leaks in high-concurrency scenarios
- Timeout handling for slow queries

### Schema Engine
#### Fixed
- Parser errors with special characters in table names
- Issues with nullable foreign keys

### SQLite Engine
#### Fixed
- Memory leaks in prepared statement cache
- Transaction rollback issues

---

## [3.1.0] - 2025-11-10

### Query Engine
#### Added
- Advanced aggregation functions (PERCENTILE, MEDIAN)
- Support for CTEs (Common Table Expressions)
- Improved query optimization

### Schema Engine
#### Added
- Enhanced `.table.cube` file parsing
- Support for custom constraints
- Index management

### SQLite Engine
#### Improved
- Transaction handling and ACID compliance
- Better prepared statement reuse

---

## [3.0.0] - 2025-10-25

### Query Engine
#### Added
- Initial release with MySQL, PostgreSQL, and SQLite support
- MongoDB integration
- Connection pooling with health checks
- Circuit breaker pattern for fault tolerance

### Schema Engine
#### Added
- Initial release
- Schema migration system
- Table creation from `.table.cube` files
- Foreign key management

### SQLite Engine
#### Added
- Initial release
- Full SQLite3 support
- Async query execution
- Prepared statement support

---

## Platforms Supported

All versions support the following platforms:
- Windows x64
- Windows ARM64
- Linux x64
- Linux ARM64
- macOS x64 (Intel)
- macOS ARM64 (Apple Silicon M1/M2)
