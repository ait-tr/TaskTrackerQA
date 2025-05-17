# TaskTrackerQA

**TaskTrackerQA** is a test automation project for the Task Tracker application. It includes **UI**, **API**, and **database** test coverage using Java, Selenium, Rest Assured, TestNG, and JDBC. The architecture follows the Page Object Model and supports modular testing through reusable repository components.

## 🚀 Technologies Used

- Java 17+
- Gradle
- TestNG
- Selenium WebDriver (UI Testing)
- Rest Assured (API Testing)
- JDBC + HikariCP (Database Testing)
- Logback (Logging)
- MySQL
- Page Object Model (POM)

## 📁 Project Structure

```
src/
├── main/java/qa/
│   ├── config/           # DB configuration
│   ├── model/            # AppUser, ConfirmCode POJOs
│   ├── mapper/           # ResultSet → POJO mappers
│   └── repository/       # SQL queries, repositories, exceptions
├── test/java/qa/
│   └── tests/
│       ├── ui/           # UI tests with Selenium
│       ├── api/          # API tests with Rest Assured
│       └── db/           # Database tests via JDBC repositories
build.gradle.kts
```

## ⚙️ Setup Instructions

1. Install **JDK 17+**
2. Set up a **MySQL** instance with required tables and data
3. Configure DB credentials in `DdConnectionProperty.java`:
   ```java
   DB_HOST, DB_PORT, DB_NAME, DB_USER, DB_PASS
   ```

## ▶️ Running Tests

To build and run all tests:

```bash
./gradlew clean test
```

Test execution is handled via **TestNG**. Test classes use `@Test` and `@DataProvider` annotations for flexible parameterization.

## 🧪 Test Coverage

- **UI Tests**: form input, validation, navigation, element visibility
- **API Tests**: response codes, body content, error cases
- **Database Tests**: repository logic, data persistence and retrieval

## ➕ Adding a New Entity

1. Add a POJO under `model/`
2. Define SQL queries in a new `*Sql.java` interface
3. Create a `RowMapper` class for mapping DB rows
4. Implement a new repository class extending `AbstractRepository`
5. Write corresponding tests under `test/java/qa/`
