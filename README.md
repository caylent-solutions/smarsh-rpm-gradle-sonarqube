# smarsh-rpm-gradle-sonarqube

RPM package providing SonarQube code quality analysis plugin configuration.

## What This Package Does

Applies the SonarQube Gradle plugin with convention-based defaults for project key and name. Projects can override any property in their `build.gradle`. The SonarQube server URL and authentication token are expected as environment variables.

## Tasks Provided

| Task | Description |
|---|---|
| `sonar` | Run SonarQube analysis |

## Configs and Assets

| File | Purpose | Synced To |
|---|---|---|
| `sonarqube.gradle` | Plugin application and default property configuration | `.packages/smarsh-rpm-gradle-sonarqube/` |
| `rpm-manifest.properties` | Declares SonarQube plugin dependency for buildscript classpath | `.packages/smarsh-rpm-gradle-sonarqube/` |

## Default Configuration

- Source encoding: UTF-8
- Test exclusions: `src/test/**`
- Project key: `${group}:${name}` (convention-based)
- Project name: `${name}` (convention-based)

## Project-Specific Overrides

Override defaults in your `build.gradle`:

```groovy
sonarqube {
    properties {
        property 'sonar.projectKey', 'com.example:my-service'
        property 'sonar.projectName', 'my-service'
        property 'sonar.github.repository', 'your-org/my-service'
    }
}
```

Set the SonarQube server URL via environment variable:

```bash
export SONAR_HOST_URL=https://sonar.your-company.com
export SONAR_TOKEN=your-token
```
