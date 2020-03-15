# java11-basic-archetype

Maven archetype for a java 11 project setup with base test dependencies.

Java 11 base application.

## BASE SETUP

### Dependencies

* Junit 5
* AssertJ
* Mockito

### Support

* general GitIgnore file generated using [gitignore.io](https://www.gitignore.io)

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

## POM Maven settings.xml

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
