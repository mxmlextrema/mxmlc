# Source specification

Sources are specified by recursive directories referred to as *source paths*. A source path is not taken as a source unless the respective MXMLShare manifest `source` element sets `include` to true.

## Exclude extension

When a source path is taken as a source, there may be the rare occasion of double taking the source file that belongs to an ActionScript 3 `include` directive. To solve this, the recommendation is to always name such files with an extension such as `.inc.as`, and then the respective MXMLShare manifest `source` element sets the `exclude-extension` string to `.inc.as`.

```toml
[[source]]
path = "src"
include = true
exclude-extension = ".inc.as"
```

The following is an example ActionScript 3 program demonstrating the case:

src/bath.as

```as3
package {
    public function bath():void {
        include "./bathLog.inc.as";
    }
}
```

src/bathLog.inc.as

```as3
trace("taking a bath");
```