# How to make an ORM addon

The first thing you need to do is make a fabric mod. (You can use this website: https://fabricmc.net/develop/template/).

**Make sure the mod is for the same version that ORM is!!** 

Now add this to your `gradle.properties`
The `version_number` or `version id` can be found on [Modrinth](https://modrinth.com/mod/origamikings-robotics-armor-mod/versions#all-versions).
```gradle
orm_version=(version number or id)
```
 Then add this to your `build.gradle` file.
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

Now configure your mod how you want it.

I would recommend using my [API](https://modrinth.com/mod/origamikings-api) for this. You can go [here](http://wiki.origamiking.net/origamikings-api/Using.html) to do that.

Then add Geckolib to your project Go [here](https://github.com/bernie-g/geckolib/wiki/GeckoLib-4-Installation) to do that.

Now you can start making Geckolib armors in Blockbench. 

Go to the source of ORM to see how OrigamiKing3612 adds them.
- A simple way of doing that is importing `net.origamiking.mcmods.orm.OrmMain` then going to its source. In IntelliJ Idea you can do that by control-clicking on the `OrmMain`

Now make a Recipe DataGen file (look at ORM if you don't know how) and use the methods I made to make recipes if you need it.

Lastly when you are done put the mod on Modrnith, Curseforge, or Github and open an Issue [here](https://github.com/OrigamiKing3612/OrigamiKings-Robotics-Mod) saying that you want to add an addon. Put the link to the site you put your mod on. If OrigamiKing3612 accepts your addon, it will be added to the mod's addon downloader!