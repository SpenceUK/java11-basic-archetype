# java11-basic-archetype

Maven archetype for a java 11 project setup with base test dependencies.

Java 11 base application.

## Install and using locally

clone this project, build and install into your local maven repository with this command:

```bash
mvn clean install
```

Then you can use the archetype to generate a new Java11 project in any directory using this command:

```bash
mvn archetype:generate \
  -DarchetypeGroupId=io.github.spenceuk \
  -DarchetypeArtifactId=java11-basic-archetype \
  -DarchetypeVersion=1.0
```

## BASE SETUP

### Dependencies

* Junit 5
* AssertJ
* Mockito

### Support

* general GitIgnore file generated using [gitignore.io](https://www.gitignore.io)
* checkstyle with [google java style](https://checkstyle.sourceforge.io/google_style.html)

### License, copyright and header

Automatically update license header and copyright header in each src file, default license is:

* MIT License

Easily changed in the POM select from a list of available licenses.

To see what is available:

```bash
  mvn license:license-list
```

To see the license details:

```bash
  mvn license:license-list -Ddetail
```

## Deployment

To deploy SNAPSHOT:

```bash
mvn deploy
```

To update version number:

```bash
mvn versions:set -DnewVersion=1.2.3
```

To deploy a RELEASE:

```bash
mvn clean deploy -P release
```

To deploy with SCM managed:

```bash
mvn release:clean release:prepare
```

answer relase and tag prompts and then to RELEASE:

```bash
mvn release:perform
```

### Rollback failed deploymnet

```bash
mvn release:rollback
mvn release:clean
```

## Maven settings.xml

required settings file in your .m2 folder locally:

```xml
<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0"
      xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
      xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0
                          http://maven.apache.org/xsd/settings-1.0.0.xsd">
  <servers>
    <server>
      <id>ossrh</id>
      <username>your-jira-id</username>
      <password>your-jira-pwd</password>
    </server>
  </servers>
  <profiles>
    <profile>
      <id>ossrh</id>
      <activation>
        <activeByDefault>true</activeByDefault>
      </activation>
      <properties>
        <gpg.executable>gpg2</gpg.executable>
        <gpg.passphrase>the_pass_phrase</gpg.passphrase>
      </properties>
    </profile>
  </profiles>
</settings>
```
