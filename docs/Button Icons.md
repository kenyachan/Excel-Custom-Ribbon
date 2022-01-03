# Button Icons

Button icons are defined within the `<button />` tag in *customUI14.xml*.

> *MSO icons are the Microsoft Office icons. They are quick simple and easier to use than custom icons and will help you keep a consistent look through your ribbon.*
>
> *A full list of them can be found [here](https://www.microsoft.com/en-au/download/details.aspx?id=21103).*
>
> ``` XML
> <button id="Button_1_btn" label="Button 1" size="large" onAction="public.Sub.reference" imageMso="ShowFrom" />
> ```

## Creating your first button with a custom icon

> *Custom icons can be used if you cannot find a suitable icon from the MSO gallery.*

Create a folder with the *customUI* folder called *images*.

Download this [Microsoft Word icon](https://i.imgur.com/31R3NvL.png) and place it in the *images* folder.

Rename the icon to *Word.png*.

Open the Workbook with 7-zip and extract *[Content_Types].xml*

Add the following into [Content_Types].xml:

``` XML
<Default Extension="png" ContentType="image/png"/>
```

> *If you have multiple icons of different format, you will need to add a line for each of the different file types.*

Save, close and replace the file in the Excel archive.

Create a folder in the customUI folder called *_rels*.

Create a file called *customUI14.xml.rels* and paste in the following:

``` XML
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<Relationships xmlns="http://schemas.openxmlformats.org/package/2006/relationships">
    <Relationship Id="WordImg" Type="http://schemas.openxmlformats.org/officeDocument/2006/relationships/image" Target="images/Word.png"/>
</Relationships>
```

> **Id** is the what you will refer to in the `<Button />` tag.  
> **Target** is the *relative* path to the image file.

In the customUI14.xml, add replace `imageMso` with image and set the value to the *Id* of the image as defined in *customUI14.xml.rels*.

``` XML
<button id="Button_1_btn" label="Button 1" size="large" onAction="public.Sub.reference" image="WordImg" />
```

Add all files back to the Excel archive.

Opening the Excel file will now show the custom ribbon with the custom button icon.

![Custom Ribbon with custom button icon](https://i.imgur.com/Rxdyzje.png)
