TaskTrackerQA
TaskTrackerQA is a test automation project for the Task Tracker application. It includes UI, API, and database test coverage using Java, Selenium, Rest Assured, TestNG, and JDBC. The architecture follows the Page Object Model and supports modular testing through reusable repository components.

🚀 Technologies Used
Java 17+

Gradle

TestNG

Selenium WebDriver (UI Testing)

Rest Assured (API Testing)

JDBC + HikariCP (Database Testing)

Logback (Logging)

MySQL

Page Object Model (POM)

📁 Project Structure
bash
Copy
Edit
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
⚙️ Setup Instructions
Install JDK 17+

Set up a MySQL instance with required tables and data

Configure DB credentials in DdConnectionProperty.java:

java
Copy
Edit
DB_HOST, DB_PORT, DB_NAME, DB_USER, DB_PASS
▶️ Running Tests
To build and run all tests:

bash
Copy
Edit
./gradlew clean test
Test execution is handled via TestNG. Test classes use @Test and @DataProvider annotations for flexible parameterization.

🧪 Test Coverage
UI Tests: form input, validation, navigation, element visibility

API Tests: response codes, body content, error cases

Database Tests: repository logic, data persistence and retrieval

➕ Adding a New Entity
Add a POJO under model/

Define SQL queries in a new *Sql.java interface

Create a RowMapper class for mapping DB rows

Implement a new repository class extending AbstractRepository

Write corresponding tests under test/java/qa/
