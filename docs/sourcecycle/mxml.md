# MXML source cycle

MXML sources go through compiler phases asynchronously.

Every MXML component belongs to an ActionScript 3 package, which is determined according to the source path matching its path.

* For example, given that the set of source paths is (`src/`) and the MXML component is `src/com/expert/ui/StatusBar.mxml`, the MXML component belongs to the `com.expert.ui` package.