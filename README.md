### 1. Gradle command

```shell

# clean
$ gradle clean

# binary
$ gradle classes

# build
$ gradle build

# skip test
$ gradle build -x test
```

### 2. Configuration: locale mirror

* step1: Create new file to ~/.gradle/init.gradle
* step2: configure mirror below;  [Refer](https://developer.aliyun.com/mvn/guide)
 
```shell
buildscript {
    repositories {
        mavenLocal()
        mavenCentral()
        maven { url 'https://maven.aliyun.com/repository/central' }
        maven { url 'https://maven.aliyun.com/repository/public' }
    }
}

allprojects {
  repositories {
    mavenLocal()
    mavenCentral()

    maven {
        url 'https://maven.aliyun.com/repository/public/'
    }
    maven {
        url 'https://maven.aliyun.com/repository/spring/'
    }
  }
}

```

### 3. gradle wrapper

* Intro: project with gradle, the version may be not match your local's, command same as `gradle`
* gradle wrapper commands as below
```shell
# clean
$ gradlew clean
$ gradlew build
# ... and so on ...
```
* upgrade `gradle wrapper` version
```shell
$ gradle wrapper --gradle-version=7.6
```

### 4. config local gradle in idea


> settings -> build tool -> gradle -> Use Gradle from : Specified location : `/opt/homebrew/Cellar/gradle/7.6/libexec`
