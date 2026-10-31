# Database tests

GitHub Actions runs the test suite in a single `build` matrix job on Windows (all target frameworks) and Ubuntu (.NET 10 only). Both jobs run the tests against a SQL Server 2019 Developer container started with Docker.

The job generates a cryptographically random SQL Server password for each run and masks it in the Actions logs. The SQL Server integration tests use `SQLSERVER_TEST_CONNECTION_STRING` when set. The configured login must be able to create and drop the `NLogTest` database.

When running locally without the variable set, the tests fall back to LocalDB (`(localdb)\MSSQLLocalDB`) with Integrated Security. To run the SQL Server tests against a local container, set `SQLSERVER_TEST_CONNECTION_STRING` to a connection string for that instance.
