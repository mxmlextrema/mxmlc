# User interface themes

The MX framework supports linking cascading style sheet files against a mx.ui.Theme subclass.

- The `PropertyReference(name)` CSS calls resolve to a property within the mx.ui.Theme subclass scope, whether it is a static property or an instance property.

```as3
package
{
    import mx.ui.*;

    [Theme(stylesheet = "style.css")]
    public class RockTheme extends Theme
    {
    }
}
```