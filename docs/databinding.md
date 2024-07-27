# Data binding

## Syntax

MXML attributes identifying Bindable properties may contain an interpolated braces group containing an ActionScript 3 expression that is either a string literal or a member expression.

- When that braces group contains a string literal, it behaves as an escaped string that may contain braces.
- When that braces group contains a member expression, the compiler resolves that expression to a Bindable property and listens to the respective `PropertyChangeEvent` event, always computing the property on change.

## Bindable meta-data

The `[Bindable]` ActionScript 3 meta-data is used to indicate that either a property or all properties of a class trigger a `PropertyChangeEvent` after write. The event is only dispatched if `newValue !== prevValue` (notice the strict `!==` operator).

The `[Bindable]` meta-data may be in one of the forms:

```
[Bindable]
[Bindable("eventName")]
[Bindable(event="eventName")]
```

If the event name is omitted, it defaults to `"propertyChange"`.

A setter may contain the `[Bindable]` meta-data, behaving similiarly as above, indicating that the parent virtual slot contains a specific `Bindable` event name.

To support `[Bindable]`, the bytecode generator generates event dispatch code right after the property's assignment, whether within a destructuring assignment that affects the enclosing class's instance or a direct assignment.