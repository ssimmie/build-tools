# build-tools

![](https://github.com/ssimmie/build-tools/workflows/ci/badge.svg)

## Usage

Add this private repository to your projects pom.

```xml
<repositories>
    <repository>
      <id>github</id>
      <name>GitHub Apache Maven Packages</name>
      <url>https://maven.pkg.github.com/ssimmie/maven-repository</url>
      <releases>
        <enabled>true</enabled>
      </releases>
      <snapshots>
        <enabled>true</enabled>
      </snapshots>
    </repository>
  </repositories>
  <pluginRepositories>
    <pluginRepository>
        <id>github</id>
        <name>GitHub Apache Maven Packages</name>
        <url>https://maven.pkg.github.com/ssimmie/maven-repository</url>
        <releases>
          <enabled>true</enabled>
        </releases>
        <snapshots>
          <enabled>true</enabled>
        </snapshots>
    </pluginRepository>
  </pluginRepositories>
```

Include dependency in your pom:

```xml
  <dependencyManagement>
    <dependencies>
      <dependency>
        <groupId>net.ssimmie</groupId>
        <artifactId>build-tools</artifactId>
        <version>20200316.04375ea</version>
      </dependency>
    </dependencies>
  </dependencyManagement>
```

```xml
<build>
  <plugins>
    <plugin>
      <groupId>org.apache.maven.plugins</groupId>
      <artifactId>maven-checkstyle-plugin</artifactId>
      <version>${maven-checkstyle-plugin.version}</version>
      <dependencies>
        <dependency>
          <groupId>net.ssimmie</groupId>
          <artifactId>build-tools</artifactId>
          <version>20200316.04375ea</version>
        </dependency>
      </dependencies>
      <configuration>
        <configLocation>ssimmie/checkstyle.xml</configLocation>
      </configuration>
      <executions>
        <execution>
          <goals>
            <goal>check</goal>
          </goals>
        </execution>
      </executions>
    </plugin>
  </plugins>
</build>
```
