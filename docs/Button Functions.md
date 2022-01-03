# Button Functions

In the VBA editor, create a new module and rename it to *RibbonButtons*.

Paste the following code into the module:

``` VB
Private Sub DoSomething(control As IRibbonControl)
    MsgBox "Hello World!"
End Sub
```

Save the file as an Excel Macro-Enabled Workbook.

In the *customUI14.xml*, change the first button's `onAction` value to `RibbonButtons.DoSomething`.

``` XML
<button id="Button_1_btn" label="Button 1" size="large" onAction="RibbonButtons.DoSomething" image="WordImg" />
```

Add the *customUI14.xml* file back into the archive.

Now when you click on *Button 1*, a message box should pop up.
