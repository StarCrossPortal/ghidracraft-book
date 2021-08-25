# Color Congiguration Support

## Extra Color Configure

A new file is added to the final distribution: `GHIDRACRAFT_INSTALLATION/support/Color.properties`.

In this file, internal colors are defined, and the ghidra should follow this file to get the color.

Currently, not all colors are defined there, so still not all colors are configurable.
All the colors that are configurable is already listed in this file.

If you encounter any color that is not yet configurable but really harms your eyes, feel free to [fire an issue](https://github.com/StarCrossPortal/ghidracraft/issues).

### Syntax

- Any line starts with "#" is considered comment:

```
# this is a comment
```

- Colors are defined as a single line: `name = #RGB`, for example:

```
Highlight.Global = #569cd6
```

There's nothing special about the "." (dot). The configuration treats that just part of the name.
When ghidra wants some color, it will look after this name. The dot is just for better categorizing the color names.

- The colors are possible to be referenced, in a form like `${referenced color name}`, for example:

```
Highlight.Default = ${White}
```

By default, a `Color.properties` file is already provided.

**Ghidracraft cannot work without a `Color.properties` file**.

### Desired Usage

This feature is designed to be used for those theme authors.
When somebody is willing to add a theme to Ghidracraft, by adding an extension (Java swing themes can be carried within a Ghidra extension) **and** a `Color.properties` file.

So, a user of this custom theme can just load the extension, swith the theme, replace the `Color.properties` file, and everything will be just fine.

However, this is not the case for current Ghidra because of the hardcoded colors within project.
That's why we have this feature.