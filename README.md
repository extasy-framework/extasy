## Extasy Framework Parent POM

The Extasy Framework Parent POM helps establish consistent Maven conventions by being the parent POM for other participating artifacts in Extasy Framework.

### Usage

Below you'll find the template that has to go into your project pom.xml:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>

  <parent>
    <groupId>io.extasy</groupId>
    <artifactId>extasy</artifactId>
    <version>LATEST_VERSION</version>
  </parent>

  <artifactId>ARTIFACT_NAME</artifactId>
  <version>ARTIFACT_VERSION</version>

  <developers>
    <developer>
      ...
    </developer>
  </developers>

  <licenses>
    <license>
      <name>Eclipse Public License - v 2.0</name>
      <url>https://www.eclipse.org/org/documents/epl-2.0/EPL-2.0.txt</url>
      <distribution>repo</distribution>
    </license>
  </licenses>

  <scm>
    <url>https://github.com/extasy-framework/YOUR_REPO</url>
    <connection>scm:git:git@github.com:extasy-framework/YOUR_REPO.git</connection>
    <developerConnection>scm:git:git@github.com:extasy-framework/YOUR_REPO.git</developerConnection>
    <tag>HEAD</tag>
  </scm>

</project>
```

After setting this up, it will be possible to perform:

- add license headers to all sources:

  - ```
    mvn license:format
    ```

- sort your pom according to predefined rules:

  - ```
    mvn sortpom:sort
    ```

- check source code formatting according to Google Style [reference](https://checkstyle.sourceforge.io/google_style.html):

  - ```
    mvn checkstyle:check
    ```

- deploy snapshots:

  - ```
    mvn deploy
    ```

- deploy releases:

  - ```
    mvn release:prepare
    mvn release:perform
    ```

### Prerequisites 

In order to be able to build the artifact there are some prerequisites:

- Java 11 or higher
- Maven 3.5.4 or higher
