# Source cycle

The MXML compiler handles three source formats simultaneously: ActionScript 3, MXML and CSS.

## First pass

1. For all ActionScript 3 sources, enumerate every package definition into an immutable sequence = *allPackages*.
2. For each definition in *allPackages*, declare the respective ActionScript 3 package.
3. For each MXML source, declare the respective ActionScript 3 package.

## Resolution passes

1. Let *remPackages* be a mutable clone of the *allPackages* sequence.
2. Let *remAS* be a mutable sequence containing all ActionScript 3 sources.
3. Let *remMXML* be a mutable sequence containing all MXML sources.
4. Let *remCSS* be an empty sequence.
5. While *remPackages* is non empty or *remMXML* is non empty
    1. Visit directives across *remPackages* or defer otherwise.
        1. Remove each element from *remPackages* that is of the `VerifierPhase::Finished` phase.
    2. Visit element in *remMXML* or defer otherwise.
        1. Remove each element from *remMXML* that is of the `VerifierPhase::Finished` phase.
6. For each package in *allPackages*
    1. Visit statements
7. While *remCSS* is non empty
    1. Visit directives for each *remCSS* element or defer
    2. Remove each element from *remCSS* that has been finished.
8. While *remAS* is non empty
    1. Resolve directives and then statements for each *remAS*
    2. Remove each element from *remAS* that has been finished.
0. Visit each deferred function expression or defer for a number of `MAX_CYCLES`.
10. Add verify error for each function expression that could not be resolved.
11. Finish each definition conflict, reporting any errors.
12. Reset verifier state.