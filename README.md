# How to Hide the Close Button in WPF TabSplitter
The TabSplitter control from Syncfusion allows you to organize tabbed content with resizable panels. In some scenarios, you may want to simplify the UI by hiding elements like the the close button or header tab. This is useful for restricting user interaction or maintaining a cleaner interface.

## Steps to Hide the Close Button
To hide the close button on the top-right corner of the TabSplitter:

1. Right-click the TabSplitter control in the MainWindow designer.
2. Select **Edit Template → Edit a Copy**.
3. A style for the TabSplitter control will be created in MainWindow.xaml.
4. Locate the ToggleButton named PART_CloseButton and set its Visibility to Collapsed.

## XAML Example
```XAML
<Window.Resources>
  <Style x:Key="TabSplitterStyle1" TargetType="{x:Type syncfusion:TabSplitter}">
    <Setter Property="Template">
      ...
      <ToggleButton x:Name="PART_CloseButton" Visibility="Collapsed">
        ...
      </ToggleButton>
      ...
    </Setter>
  </Style>
</Window.Resources>

<Grid>
  <syncfusion:TabSplitter Name="Tabsplit" HideHeaderOnSingleChild="True" Style="{DynamicResource TabSplitterStyle1}">
    <syncfusion:TabSplitterItem Header="tab1">
      <syncfusion:TabSplitterItem.TopPanelItems>
        <syncfusion:SplitterPage Header="Split1"/>
      </syncfusion:TabSplitterItem.TopPanelItems>
      <syncfusion:TabSplitterItem.BottomPanelItems>
        <syncfusion:SplitterPage Header="Split2"/>
      </syncfusion:TabSplitterItem.BottomPanelItems>
    </syncfusion:TabSplitterItem>
  </syncfusion:TabSplitter>
</Grid>
```
## Notes
- Customizing templates requires familiarity with WPF styles and control templates.
- Ensure you apply the style to the TabSplitter instance using Style="{DynamicResource TabSplitterStyle1}".

## Reference
- For a detailed step-by-step guide and additional examples, refer to the official Syncfusion Knowledge Base: https://www.syncfusion.com/kb/11572/how-to-hide-the-close-button-in-wpf-tabsplitter
