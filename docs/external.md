# External mode

Verification may occur in the *external* mode, where all methods must be either `abstract` or `native` and action statements and static media embedding are not allowed. In the external mode, no bytecode or SWF symbols are generated.

## Adobe AIR

The external mode is used primarily for the Adobe AIR built-ins (top-level, `flash.**.*` and `air.**.*`). The top-level includes the parameterized `Vector.<T>` for instance.

The Flex library (`mx.**.*`) is not external but part of the compiler, therefore it is not verified in external mode.