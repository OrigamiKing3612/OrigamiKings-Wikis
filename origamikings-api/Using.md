# How to use this API/Library Mod
### Add this to your `gradle.properties`
The `version_number` or `version id` can be found on [Modrinth](https://modrinth.com/mod/origamikings-api/versions)
```gradle
origamikings_api=(version id or number)
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
    modImplementation "maven.modrinth:origamikings-api:${origamikings_api}"
}
 ```