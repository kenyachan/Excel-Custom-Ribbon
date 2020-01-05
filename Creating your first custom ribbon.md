# Creating your first custom ribbon

Create a folder on your desktop called "customUI". This is case sensitive and your ribbon will not show up if it's wrong.

``` XML
Inside the customUI folder, create an XML file called "customUI14.xml" and paste in the following:
<customUI xmlns="http://schemas.microsoft.com/office/2009/07/customui">
    <ribbon startFromScratch="false">
        <tabs>
            <tab id="MyCustomTabName" label="Custom Tab">

                <group id="Group_1" label="Group 1">
                    <button id="Button_1_btn" label="Button 1" size="large" onAction="public.Sub.reference" imageMso="ShowFrom" />
                    <button id="Button_2_btn" label="Button 2" size="large" onAction="public.Sub.reference2" imageMso="CreateMailRule" />
                    <button id="Button_3_btn" label="Button 3" size="large" onAction="public.Sub.reference3" screentip="This is a screen tip" supertip="This is a super tip" imageMso="ShowBcc" />
                </group>

                <group id="Group_2" label="Group 2">
                    <button id="Button_4_btn" label="Button 4" size="normal" onAction="public.Sub.reference4" imageMso="EnvelopesAndLabelsDialog" />
                </group>

            </tab>
        </tabs>
    </ribbon>
</customUI>
```

Create another folder on your desktop called "_rels".

Inside the _rels folder, create an XML file called ".rels" and paste in the following:

``` XML
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<Relationships xmlns="http://schemas.openxmlformats.org/package/2006/relationships">
    <Relationship Id="rId1" Type="http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument" Target="xl/workbook.xml"/>
    <Relationship Id="rId6" Type="http://schemas.openxmlformats.org/officeDocument/2006/relationships/extended-properties" Target="docProps/app.xml"/>
    <Relationship Id="rId5" Type="http://schemas.openxmlformats.org/package/2006/relationships/metadata/core-properties" Target="docProps/core.xml"/>
    <!-- Added this relationship for custom ribbon UI -->
    <Relationship Id="rId4" Type="http://schemas.microsoft.com/office/2007/relationships/ui/extensibility" Target="customUI/customUI14.xml"/>
</Relationships>
```

Rename the .rels.xml file to remove the file extension
i.e. .rels.xml -> .rels

You should now have 2 folders on your desktop.

Create a new Excel workbook and save it to your desktop.
Open the workbook with 7-zip and drag in the two folders you just created.

Congratulations, you've now created your first custom ribbon!
Open the workbook and your custom ribbon should show up the top.
