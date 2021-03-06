ProPatcher
==========
ProPatcher is a Gradle plugin for creating patch files on the go.

**ProPatcher requires Java 1.8**

## Installation
ProPatcher has been added to Gradle's plugin portal, and can be used using the new
plugin mechanism introduced in Gradle 2.1.
You can find the plugin [here](https://plugins.gradle.org/plugin/uk.jamierocks.propatcher).

```gradle
plugins {
    id 'uk.jamierocks.propatcher' version '1.2.3'
}
```

For those of you, using builds where you cannot utilise the new plugin mechanism,
or are using a version of Gradle prior to 2.1, here is the old example:

```gradle
buildscript {
    repositories {
        maven {
            url 'https://plugins.gradle.org/m2/'
        }
    }
    dependencies {
        classpath 'gradle.plugin.uk.jamierocks:propatcher:1.2.3'
    }
}

apply plugin: 'uk.jamierocks.propatcher'
```

## Example
```gradle
patches {
    root = file('root') // This is a directory
    target = file('target') // This is also a directory
    patches = file('patches') // This is again a directory
}
```

## Tasks
| Name           | Description                                           |
| -------------- | ----------------------------------------------------- |
| `makePatches`  | Make all necessary patch files.                       |
| `applyPatches` | Apply all patches to the target.                      |
| `resetSources` | Resets the target, to it's original unmodified state. |
