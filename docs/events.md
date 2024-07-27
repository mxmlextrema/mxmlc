# Events

## Event meta-data

The `[Event]` meta-data is used to indicate an event that is likely dispatched in a class or interface.

It may define the following properties:

- `name="eventName"` - Specifies the event type string.
- `type="XEvent"` - Specifies the class that represents the event object.
- `bubbles="true|false"` - Specifies whether the event is dispatched in the bubbling phase or not.

It may contain an ASDoc comment containing the following tags:

- `@eventType XEvent.Y` - Specifies a class static constant identifying the event as a string.
- `@eventType String` - Indicates that the event may be identified by any string.