# Database tests

GitHub Actions runs the test suite on Windows and Ubuntu. Windows uses LocalDB; Ubuntu targets .NET 8 and runs against a SQL Server 2019 Developer container.

The SQL Server integration tests use `SQLSERVER_TEST_CONNECTION_STRING` when set. The configured login must be able to create and drop the `NLogTest` database. When unset, Windows tests use LocalDB; Linux tests require the variable to point to a SQL Server instance.
