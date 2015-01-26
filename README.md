
#### Forked from [aaronfreeman/play-lombok](https://github.com/aaronfreeman/play-lombok)

# Lombok for PlayFramework1

This module adds Lombok to PlayFramework1.

## Env

* Play! Framework 1.2.5
* Eclipse Luna


## Install

#### Install lombok.jar

Download lombok.jar from [Project Lombok](http://projectlombok.org/)

    $ wget http://projectlombok.org/downloads/lombok.jar
    $ mv lombok.jar /your/eclipse/folder (ex. /Applications/eclipse/Eclipse.app/Contents/MacOS/ )

#### Modify eclipse.ini

    $ cd /your/eclipse/folder (ex. /Applications/eclipse/Eclipse.app/Contents/MacOS/ )
    $ vim eclipse.ini
    -javaagent:/Applications/eclipse/Eclipse.app/Contents/MacOS/lombok.jar
    -Xbootclasspath/a:/Applications/eclipse/Eclipse.app/Contents/MacOS/lombok.jar

#### Install play-lombok module

    $ play new SampleProject
    $ vim SampleProject/conf/dependencies.yml

    require:
        - play
        - org.projectlombok -> lombok 1.14.8
        - asufana -> play-lombok 1.2.3

    repositories:
        - asufana_zip_repo:
            type:       http
            artifact:   https://github.com/asufana/[module]/raw/master/dist/[module]-[revision].zip
            contains:
                - asufana -> play-lombok

    $ play deps SampleProject --clearcache
    $ play ec SampleProject

#### Set vm option

- Eclipse > Preferences > Java > Installed JREs
- Select JRE and Edit
- Default VM arguments

```
-javaagent:{your eclipse directory}/lombok.jar
 (ex. -javaagent:/Applications/eclipse/Eclipse.app/Contents/MacOS/lombok.jar )
```



