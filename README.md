# smarsh-rpm-gradle-sonarqube

RPM package providing SonarQube code quality analysis plugin configuration.

## Provided Tasks

- `sonar` - Run SonarQube analysis

## Default Configuration

- Source encoding: UTF-8
- Test exclusions: `src/test/**`
- Project key: `${group}:${name}` (convention-based)
- Project name: `${name}` (convention-based)

## Project-Specific Overrides

Override defaults in your `build.gradle`:

sonarqube {
    properties {
        property 'sonar.projectKey', 'com.example:my-service'
        property 'sonar.projectName', 'my-service'
        property 'sonar.github.repository', 'your-org/my-service'
    }
}

Set the SonarQube server URL via environment variable:

export SONAR_HOST_URL=https://sonar.your-company.com
export SONAR_TOKEN=your-token
