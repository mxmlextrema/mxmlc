# Embedding

There are several ways of embedding static media in ActionScript 3 programs. Both ActionScript 3, MXML and CSS have a way of embedding static media.

- ActionScript 3 uses the `[Embed]` meta data either in classes or variables.
- CSS uses the `Embed()` function.
- CSS uses `@font-face` statements that embed a local or system font.

## Embed meta-data

The `[Embed]` ActionScript 3 meta-data is used in two different ways:

* It may appear in a class definition in which case it must extend the right class
* It may appear in a `static` variable definition, consisting of only one binding, possibly `const` (without initializer), strictly typed `Class`.