
# MathUtils Java Project with JUnit Testing and Jenkins Integration

This project demonstrates Java unit testing using JUnit, integrated with Jenkins for continuous integration (CI), static code analysis (SonarQube), code coverage (JaCoCo), artifact generation, and build notifications. The MathUtils class includes basic mathematical operations with proper error handling, and the project setup ensures robust testing and continuous feedback on code quality.

## Project Structure

- **MathUtils.java**: A Java class with basic mathematical operations.
  - `int add(int a, int b)`: Adds two integers.
  - `int subtract(int a, int b)`: Subtracts `b` from `a`.
  - `int multiply(int a, int b)`: Multiplies two integers.
  - `double divide(int a, int b)`: Divides `a` by `b`, returns `-1.0` if `b` is zero.

- **MathUtilsTest.java**: A JUnit test class for unit testing the methods in `MathUtils.java`. It includes various test cases for valid inputs and edge cases.
  
- **pom.xml**: Maven build file that includes the configurations for dependencies, static analysis (SonarQube), and code coverage (JaCoCo).

## Getting Started

### Prerequisites

- **Java 11 or later** installed.
- **Maven** for building the project.
- **JUnit 5** for running unit tests.
- **Jenkins** installed locally or using an online Jenkins environment.
- **SonarQube** for static code analysis.
- **JaCoCo** for code coverage.
- A version control system like **Git**.

### Clone the Repository

```bash
git clone https://github.com/yourusername/MathUtils-Jenkins.git
cd MathUtils-Jenkins
```

### Building the Project

Use Maven to build the project:

```bash
mvn clean install
```

This will compile the `MathUtils.java` class, run the unit tests in `MathUtilsTest.java`, and generate the necessary reports.

### Running the Tests

You can run the JUnit tests separately using:

```bash
mvn test
```

### SonarQube Static Code Analysis

1. Make sure SonarQube is running locally or is accessible via an external server.
2. Update the **pom.xml** file to include your SonarQube token.
3. Run the SonarQube analysis:

```bash
mvn sonar:sonar
```

You can view the analysis results on the SonarQube dashboard.

### Code Coverage with JaCoCo

JaCoCo is configured in **pom.xml** to generate code coverage reports. After running tests, the coverage report will be available in the `target/site/jacoco` folder.

```bash
mvn jacoco:report
```

### Jenkins Integration

1. Install Jenkins on your machine or use a cloud Jenkins instance.
2. Create a Jenkins job that pulls this repository from GitHub.
3. Configure the job to:
   - Build the project using Maven.
   - Run unit tests and generate reports.
   - Run SonarQube for static code analysis.
   - Generate a code coverage report with JaCoCo.
   - Create a deployable artifact (JAR file).
   - Send notifications on build success or failure.

### Artifact Generation

Upon successful build, Jenkins will generate a deployable JAR file named `mathutil-1.0-SNAPSHOT.jar` as part of the post-build process.

### Notifications

Jenkins is configured to send build notifications. You can set up email or Slack notifications in the Jenkins job configuration, ensuring that the team is notified of the build status.

## Screenshots

### Jenkins Build Results
![Jenkins Build Results](path_to_screenshot1)

### SonarQube Dashboard
![SonarQube Dashboard](path_to_screenshot2)

### JaCoCo Coverage Report
![JaCoCo Coverage](path_to_screenshot3)

### Generated Artifact
![Generated Artifact](path_to_screenshot4)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
