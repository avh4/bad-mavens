## Bad Maven

*noun, informal*

1. A software developer who does not publish his/her open-source projects in a way that is easily usable by others (i.e., on maven central).

This github repository is a maven repository that hosts jar for projects whose
owners are b admavens.  Pull requests adding jars for open-source projects that
do not publish their own jars on maven central are welcome.

### Usage

Add the following to your `pom.xml`:

```xml
  <repositories>
    <repository>
      <id>avh4-bad-mavens</id>
      <url>https://github.com/avh4/bad-mavens/raw/master</url>
    </repository>
  </repositories>
```

### Adding more artifacts

```bash
git clone http://github.com/avh4/bad-mavens.git
cd bad-mavens
mvn deploy:deploy-file -Dfile=<full-path-to-jar> -DgroupId=<groupid> -DartifactId=<artifactid> -Dversion=<version> -Dpackaging=jar -Durl=file://"`pwd`"
git add .
git commit -m "Added <groupid>:<artifactid>:<version>:jar from <link to project website>"
```

