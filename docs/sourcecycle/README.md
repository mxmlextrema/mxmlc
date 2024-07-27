# Source cycle

The MXML compiler handles three source formats simultaneously: ActionScript 3, MXML and CSS.

## First pass

1. For all ActionScript 3 sources, enumerate every package definition into an immutable sequence = *allPackages*.
2. For each definition in *allPackages*, declare the respective ActionScript 3 package.
3. Let *remPackages* be a mutable clone of the *allPackages* sequence.

## Second pass

1. Let *remCSS* be an empty sequence.
2. 