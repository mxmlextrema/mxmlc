# Source cycle

The MXML compiler handles three source formats simultaneously: ActionScript 3, MXML and CSS.

## First pass

1. For all ActionScript 3 sources, enumerate every package definition into an immutable sequence = *allPackages*.
2. For each definition in *allPackages*, declare the respective ActionScript 3 package.
3. For each MXML source, declare the respective ActionScript 3 package.
4. Let *remPackages* be a mutable clone of the *allPackages* sequence.

## Second pass

1. Let *remAS* be a mutable sequence containing all ActionScript 3 sources.
2. Let *remMXML* be a mutable sequence containing all MXML sources.
3. Let *remCSS* be an empty sequence.
4. While *remPackages* is non empty or *remMXML* is non empty
    1. Visit directives across *remPackages* or defer otherwise.
        1. Remove each element from *remPackages* that is of the `VerifierPhase::Finished` phase.
    2. Visit element in *remMXML* or defer otherwise.
        1. Remove each element from *remMXML* that is of the `VerifierPhase::Finished` phase.
5. For each package in *allPackages*
    1. Visit statements
6. While *remCSS* is non empty
    1. (place steps here)
7. While *remAS* is non empty
    1. (place steps here)