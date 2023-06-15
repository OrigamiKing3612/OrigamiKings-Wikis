# How to make an ORM addon

The first thing you need to do is make a fabric mod. (You can use this website: https://fabricmc.net/develop/template/)

**Make sure the mod is for the same version that ORM is!!** 

Now add this to your `gradle.properties`
The `version_number` or `version id` can be found on [Modrinth](https://modrinth.com/mod/origamikings-robotics-armor-mod/versions#all-versions)
```gradle
orm_version=(version number or id)
```
### Add this to your `build.gradle`
 ```gradle
 repositories {
    exclusiveContent {
        forRepository {
            maven {
                name = "Modrinth"
                url = "https://api.modrinth.com/maven"
            }
        }
        filter {
            includeGroup "maven.modrinth"
        }
    }
}
dependencies {
    modImplementation "maven.modrinth:origamikings-robotics-armor-mod:${orm_version}"
}
 ```

Work in Progress