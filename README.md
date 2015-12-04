# fayde-multibinding
Multi-binding for Fayde framework.

## Multivalue Converter
Create a new IMultiValueConverter. This feature takes in a collection of Bindings

https://msdn.microsoft.com/en-us/library/system.windows.data.imultivalueconverter(v=vs.110).aspx

Name|Description
----|-----------
Convert(Object[], Type, Object, CultureInfo)|Converts source values to a value for the binding target. The data binding engine calls this method when it propagates the values from source bindings to the binding target.
ConvertBack(Object, Type[], Object, CultureInfo)|Converts a binding target value to the source binding values.

###example
```xml
<TextBox.Text>                                              
 <MultiBinding Converter="{StaticResource myConverter}">
   <Binding RelativeSource="{RelativeSource TemplatedParent}" Path="SelectedValue"/>
   <Binding RelativeSource="{RelativeSource TemplatedParent}" Path="NullText"/>
 </MultiBinding>                                              
</TextBox.Text>
```

## MultiBinding Class
https://msdn.microsoft.com/en-us/library/system.windows.data.multibinding(v=vs.110).aspx

```
[ContentPropertyAttribute("Bindings")]
public class MultiBinding : BindingBase
```

###example
```
<TextBlock>
    <TextBlock.Text>    
        <MultiBinding StringFormat="{}{0} + {1}">
            <Binding Path="Name" />
            <Binding Path="ID" />
        </MultiBinding>
    </TextBlock.Text>
</TextBlock>
```
