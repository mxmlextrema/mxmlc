# Source cycle

The MXML compiler handles three source formats simultaneously: ActionScript 3, MXML and CSS.

## First pass

1. For all ActionScript 3 sources, enumerate every package definition into an immutable sequence = *allPackageDefinitions*.
2. For each definition in *allPackageDefinitions*, declare the respective ActionScript 3 package.
3. Let *remainingPackageDefinitions* be a mutable clone of the *allPackageDefinitions* sequence.

## Second pass