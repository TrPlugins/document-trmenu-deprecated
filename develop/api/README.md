# API

Maven:
```xml
    <repositories>
      <repository>
        <id>roselle-public</id>
        <url>https://repo.iroselle.com/repository/maven-public/</url>
      </repository>
    </repositories>

    <dependencies>
      <dependency>
        <groupId>me.arasple</groupId>
        <artifactId>trmenu</artifactId>
        <version>{LATEST-VERSION}</version>
        <scope>provided</scope>
      </dependency>
    </dependencies>
```

Gradle Kotlin DSL
```kotlin
repositories {
  maven("https://repo.iroselle.com/repository/maven-public/")
}
dependencies {
  compileOnly("me.arasple:TrMenu:{LATEST-VERSION}")
}

```