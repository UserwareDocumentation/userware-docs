# Class ContentControl

View the class and its metadata.

<table class="metadata-table">
  <thead>
    <tr class="metadata-header-row">
      <th class="metadata-header-label">Property</th>
      <th class="metadata-header-value">Details</th>
    </tr>
  </thead>
  <tbody>
    <tr class="metadata-row">
      <td class="metadata-label">Namespace</td>
      <td class="metadata-value">System.Windows.Controls</td>
    </tr>
    <tr class="metadata-row">
      <td class="metadata-label">Assembly</td>
      <td class="metadata-value">
        OpenSilver.dll
        <a href="https://www.nuget.org/packages/OpenSilver" class="nuget-link" target="_blank">
          <img src="resources/studio.support/local/images/nuget-logo.png">
        </a>
      </td>
    </tr>
    <tr class="metadata-row">
      <td class="metadata-label">Source</td>
      <td class="metadata-value">
        <a href="https://github.com/OpenSilver/OpenSilver/blob/develop/src/Runtime/Runtime/System.Windows.Controls/ContentControl.cs" target="_blank">
          <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" style="vertical-align:middle;margin-right:4px;"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.387.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.725-4.042-1.61-4.042-1.61-.546-1.387-1.333-1.756-1.333-1.756-1.087-.745.083-.729.083-.729 1.205.084 1.838 1.237 1.838 1.237 1.07 1.835 2.809 1.305 3.495.998.107-.776.418-1.305.762-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.47-2.38 1.236-3.22-.123-.303-.536-1.523.117-3.176 0 0 1.008-.322 3.3 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.29-1.552 3.295-1.23 3.295-1.23.655 1.653.242 2.873.12 3.176.77.84 1.235 1.91 1.235 3.22 0 4.61-2.804 5.625-5.475 5.92.43.372.823 1.102.823 2.222 0 1.606-.015 2.896-.015 3.286 0 .32.216.694.825.576 4.765-1.588 8.2-6.084 8.2-11.386 0-6.627-5.373-12-12-12z"/></svg>
          src/Runtime/Runtime/System.Windows.Controls/ContentControl.cs
        </a>
      </td>
    </tr>
  </tbody>
</table>

Represents a control with a single piece of content. Controls such as Button, CheckBox, and ScrollViewer directly or indirectly inherit from this class.


## Syntax

View the syntax of this element.

[tabgroup]
[tab=C#]
```
public class ContentControl : Control, IInputElement, ISupportInitialize
```
[/tab]
[/tabgroup]

## Inheritance

Explore the class inheritance hierarchy.

[hierarchy]
- class: Object
  namespace: System
  level: 1
- class: DispatcherObject
  namespace: System.Windows.Threading
  level: 2
  parent: Object
  url: /opensilver/12648
- class: DependencyObject
  namespace: System.Windows
  level: 3
  parent: DispatcherObject
  url: /opensilver/11834
- class: UIElement
  namespace: System.Windows
  level: 4
  parent: DependencyObject
  url: /opensilver/11957
- class: FrameworkElement
  namespace: System.Windows
  level: 5
  parent: UIElement
  url: /opensilver/11875
- class: Control
  namespace: System.Windows.Controls
  level: 6
  parent: FrameworkElement
  url: /opensilver/12096
- class: ContentControl
  namespace: System.Windows.Controls
  level: 7
  parent: Control
  url: /opensilver/12090
  highlight: true
[/hierarchy]


## Derived Classes

View derived classes.

[reference=3]
- class: ChildWindow
  namespace: System.Windows.Controls
  url: /opensilver/12080
- class: ButtonBase
  namespace: System.Windows.Controls.Primitives
  url: /opensilver/12169
- class: SelectorItem
  namespace: System.Windows.Controls.Primitives
  url: /opensilver/12195
- class: ScrollViewer
  namespace: System.Windows.Controls
  url: /opensilver/12136
- class: ToolTip
  namespace: System.Windows.Controls
  url: /opensilver/12152
- class: Viewbox
  namespace: System.Windows.Controls
  url: /opensilver/12162
[/reference]


## Implements

See implemented interfaces.

[reference=4]
- class: ISupportInitialize
  namespace: System.ComponentModel
- class: IInputElement
  namespace: System.Windows
  url: /opensilver/11888
[/reference]


## Inherited Members

Check inherited members.

[inherited]
- class: Object
  namespace: System
  members:
    - Equals(System.Object,System.Object)
    - Equals(System.Object)
    - GetHashCode
    - GetType
    - MemberwiseClone
    - ReferenceEquals(System.Object,System.Object)
    - ToString
- class: Control
  namespace: System.Windows.Controls
  url: /opensilver/12096
  members:
    - ApplyTemplate
    - ArrangeOverride(System.Windows.Size)
    - Background
    - BackgroundProperty
    - BorderBrush
    - BorderBrushProperty
    - BorderThickness
    - BorderThicknessProperty
    - CharacterSpacing
    - CharacterSpacingProperty
    - CreateDomElement(System.Object,System.Object@)
    - EnableBaseControlHandlingOfVisualStates
    - Focus
    - FontFamily
    - FontFamilyProperty
    - FontSize
    - FontSizeProperty
    - FontStretch
    - FontStretchProperty
    - FontStyle
    - FontStyleProperty
    - FontWeight
    - FontWeightProperty
    - Foreground
    - ForegroundProperty
    - GetTemplateChild(System.String)
    - HandlesScrolling
    - HorizontalContentAlignment
    - HorizontalContentAlignmentProperty
    - IsTabStop
    - IsTabStopProperty
    - MeasureOverride(System.Windows.Size)
    - MouseDoubleClick
    - MouseDoubleClickEvent
    - OnApplyTemplate
    - OnDragEnter(System.Windows.DragEventArgs)
    - OnDragLeave(System.Windows.DragEventArgs)
    - OnDrop(System.Windows.DragEventArgs)
    - OnGotFocus(System.Windows.RoutedEventArgs)
    - OnLostFocus(System.Windows.RoutedEventArgs)
    - OnMouseDoubleClick(System.Windows.Input.MouseButtonEventArgs)
    - OnTextInputUpdate(System.Windows.Input.TextCompositionEventArgs)
    - Padding
    - PaddingProperty
    - TabIndex
    - TabIndexProperty
    - TabNavigation
    - TabNavigationProperty
    - Template
    - TemplateProperty
    - TextDecorations
    - TextDecorationsProperty
    - VerticalContentAlignment
    - VerticalContentAlignmentProperty
- class: DependencyObject
  namespace: System.Windows
  url: /opensilver/11834
  members:
    - CheckAccess
    - ClearValue(System.Windows.DependencyProperty)
    - ClearValue(System.Windows.DependencyPropertyKey)
    - CoerceValue(System.Windows.DependencyProperty)
    - DependencyObjectType
    - Dispatcher
    - GetAnimationBaseValue(System.Windows.DependencyProperty)
    - GetLocalValueEnumerator
    - GetValue(System.Windows.DependencyProperty)
    - IsSealed
    - ReadLocalValue(System.Windows.DependencyProperty)
    - SetCurrentValue(System.Windows.DependencyProperty,System.Object)
    - SetValue(System.Windows.DependencyProperty,System.Object)
    - SetValue(System.Windows.DependencyPropertyKey,System.Object)
- class: FrameworkElement
  namespace: System.Windows
  url: /opensilver/11875
  members:
    - ActualHeight
    - ActualHeightProperty
    - ActualWidth
    - ActualWidthProperty
    - AddLogicalChild(System.Object)
    - ArrangeCore(System.Windows.Rect)
    - BeginInit
    - BindingValidationError
    - ContextMenu
    - ContextMenuOpening
    - ContextMenuProperty
    - Cursor
    - CursorProperty
    - DataContext
    - DataContextChanged
    - DataContextProperty
    - DefaultStyleKey
    - DefaultStyleKeyProperty
    - EndInit
    - FindName(System.String)
    - FindResource(System.Object)
    - FlowDirection
    - FlowDirectionProperty
    - GetBindingExpression(System.Windows.DependencyProperty)
    - GetVisualChild(System.Int32)
    - Height
    - HeightProperty
    - HorizontalAlignment
    - HorizontalAlignmentProperty
    - Initialized
    - INTERNAL_OnAttachedToVisualTree
    - INTERNAL_OnDetachedFromVisualTree
    - IsInitialized
    - IsLoaded
    - Language
    - LanguageProperty
    - LayoutUpdated
    - Loaded
    - LoadedEvent
    - ManageIsEnabled(System.Boolean)
    - Margin
    - MarginProperty
    - MaxHeight
    - MaxHeightProperty
    - MaxWidth
    - MaxWidthProperty
    - MeasureCore(System.Windows.Size)
    - MinHeight
    - MinHeightProperty
    - MinWidth
    - MinWidthProperty
    - Name
    - NameProperty
    - OnInitialized(System.EventArgs)
    - OnPropertyChanged(System.Windows.DependencyPropertyChangedEventArgs)
    - OnRenderSizeChanged(System.Windows.SizeChangedInfo)
    - OnVisualParentChanged(System.Windows.DependencyObject)
    - OverridesDefaultStyle
    - OverridesDefaultStyleProperty
    - Parent
    - RegisterName(System.String,System.Object)
    - RemoveLogicalChild(System.Object)
    - ResourceLookupMode
    - Resources
    - SetBinding(System.Windows.DependencyProperty,System.Windows.Data.Binding)
    - SetBinding(System.Windows.DependencyProperty,System.Windows.Data.BindingBase)
    - SetResourceReference(System.Windows.DependencyProperty,System.Object)
    - SizeChanged
    - Style
    - StyleProperty
    - Tag
    - TagProperty
    - TemplatedParent
    - ToolTip
    - ToolTipProperty
    - Triggers
    - TryFindResource(System.Object)
    - Unloaded
    - UnloadedEvent
    - UnregisterName(System.String)
    - VerticalAlignment
    - VerticalAlignmentProperty
    - VisualChildrenCount
    - Width
    - WidthProperty
- class: UIElement
  namespace: System.Windows
  url: /opensilver/11957
  members:
    - AddHandler(System.Windows.RoutedEvent,System.Delegate,System.Boolean)
    - AddHandler(System.Windows.RoutedEvent,System.Delegate)
    - AddVisualChild(System.Windows.UIElement)
    - AllowDrop
    - AllowDropProperty
    - AllowScrollOnTouchMove
    - AllowScrollOnTouchMoveProperty
    - Arrange(System.Windows.Rect)
    - BeginAnimation(System.Windows.DependencyProperty,System.Windows.Media.Animation.AnimationTimeline)
    - CacheMode
    - CacheModeProperty
    - CaptureMouse
    - Clip
    - ClipProperty
    - ClipToBounds
    - ClipToBoundsProperty
    - CommandBindings
    - DesiredSize
    - DragEnter
    - DragLeave
    - DragOver
    - Drop
    - Effect
    - EffectProperty
    - Focusable
    - FocusableChanged
    - FocusableProperty
    - GotFocus
    - GotFocusEvent
    - GotMouseCapture
    - GotMouseCaptureEvent
    - InputBindings
    - INTERNAL_AttachToDomEvents
    - INTERNAL_DetachFromDomEvents
    - InvalidateArrange
    - InvalidateMeasure
    - InvalidateVisual
    - IsArrangeValid
    - IsEnabled
    - IsEnabledChanged
    - IsEnabledCore
    - IsEnabledProperty
    - IsHitTestVisible
    - IsHitTestVisibleChanged
    - IsHitTestVisibleProperty
    - IsMeasureValid
    - IsMouseCaptured
    - IsMouseOver
    - IsMouseOverProperty
    - IsVisible
    - IsVisibleChanged
    - IsVisibleProperty
    - KeyDown
    - KeyDownEvent
    - KeyUp
    - KeyUpEvent
    - LostFocus
    - LostFocusEvent
    - LostMouseCapture
    - LostMouseCaptureEvent
    - Measure(System.Windows.Size)
    - MouseDown
    - MouseDownEvent
    - MouseEnter
    - MouseEnterEvent
    - MouseLeave
    - MouseLeaveEvent
    - MouseLeftButtonDown
    - MouseLeftButtonDownEvent
    - MouseLeftButtonUp
    - MouseLeftButtonUpEvent
    - MouseMove
    - MouseMoveEvent
    - MouseRightButtonDown
    - MouseRightButtonDownEvent
    - MouseRightButtonUp
    - MouseRightButtonUpEvent
    - MouseUp
    - MouseUpEvent
    - MouseWheel
    - MouseWheelEvent
    - OnChildDesiredSizeChanged(System.Windows.UIElement)
    - OnCreateAutomationPeer
    - OnGotMouseCapture(System.Windows.Input.MouseEventArgs)
    - OnKeyDown(System.Windows.Input.KeyEventArgs)
    - OnKeyUp(System.Windows.Input.KeyEventArgs)
    - OnLostMouseCapture(System.Windows.Input.MouseEventArgs)
    - OnMouseDown(System.Windows.Input.MouseButtonEventArgs)
    - OnMouseEnter(System.Windows.Input.MouseEventArgs)
    - OnMouseLeave(System.Windows.Input.MouseEventArgs)
    - OnMouseLeftButtonDown(System.Windows.Input.MouseButtonEventArgs)
    - OnMouseLeftButtonUp(System.Windows.Input.MouseButtonEventArgs)
    - OnMouseMove(System.Windows.Input.MouseEventArgs)
    - OnMouseRightButtonDown(System.Windows.Input.MouseButtonEventArgs)
    - OnMouseRightButtonUp(System.Windows.Input.MouseButtonEventArgs)
    - OnMouseUp(System.Windows.Input.MouseButtonEventArgs)
    - OnMouseWheel(System.Windows.Input.MouseWheelEventArgs)
    - OnPreviewKeyDown(System.Windows.Input.KeyEventArgs)
    - OnPreviewKeyUp(System.Windows.Input.KeyEventArgs)
    - OnPreviewMouseDown(System.Windows.Input.MouseButtonEventArgs)
    - OnPreviewMouseLeftButtonDown(System.Windows.Input.MouseButtonEventArgs)
    - OnPreviewMouseLeftButtonUp(System.Windows.Input.MouseButtonEventArgs)
    - OnPreviewMouseMove(System.Windows.Input.MouseEventArgs)
    - OnPreviewMouseRightButtonDown(System.Windows.Input.MouseButtonEventArgs)
    - OnPreviewMouseRightButtonUp(System.Windows.Input.MouseButtonEventArgs)
    - OnPreviewMouseUp(System.Windows.Input.MouseButtonEventArgs)
    - OnPreviewMouseWheel(System.Windows.Input.MouseWheelEventArgs)
    - OnTapped(System.Windows.Input.TappedRoutedEventArgs)
    - OnTextInput(System.Windows.Input.TextCompositionEventArgs)
    - OnTextInputStart(System.Windows.Input.TextCompositionEventArgs)
    - OnVisualChildrenChanged(System.Windows.DependencyObject,System.Windows.DependencyObject)
    - Opacity
    - OpacityMask
    - OpacityMaskProperty
    - OpacityProperty
    - PreviewKeyDown
    - PreviewKeyDownEvent
    - PreviewKeyUp
    - PreviewKeyUpEvent
    - PreviewMouseDown
    - PreviewMouseDownEvent
    - PreviewMouseLeftButtonDown
    - PreviewMouseLeftButtonDownEvent
    - PreviewMouseLeftButtonUp
    - PreviewMouseLeftButtonUpEvent
    - PreviewMouseMove
    - PreviewMouseMoveEvent
    - PreviewMouseRightButtonDown
    - PreviewMouseRightButtonDownEvent
    - PreviewMouseRightButtonUp
    - PreviewMouseRightButtonUpEvent
    - PreviewMouseUp
    - PreviewMouseUpEvent
    - PreviewMouseWheel
    - PreviewMouseWheelEvent
    - Projection
    - ProjectionProperty
    - RaiseEvent(System.Windows.RoutedEventArgs)
    - ReleaseMouseCapture
    - RemoveHandler(System.Windows.RoutedEvent,System.Delegate)
    - RemoveVisualChild(System.Windows.UIElement)
    - RenderSize
    - RenderTransform
    - RenderTransformOrigin
    - RenderTransformOriginProperty
    - RenderTransformProperty
    - Tapped
    - TappedEvent
    - TextInput
    - TextInputEvent
    - TextInputStart
    - TextInputStartEvent
    - TextInputUpdate
    - TextInputUpdateEvent
    - TransformToAncestor(System.Windows.UIElement)
    - TransformToDescendant(System.Windows.UIElement)
    - TransformToVisual(System.Windows.UIElement)
    - UpdateLayout
    - UseLayoutRounding
    - UseLayoutRoundingProperty
    - Visibility
    - VisibilityProperty
    - VisualParent
    - XamlSourcePath
[/inherited]



## Constructors

### ContentControl()

Initializes a new instance of the [ContentControl](/opensilver/12090) class.

**Declaration**

[tabgroup]
[tab=C#]
```
public ContentControl()
```
[/tab]
[/tabgroup]


## Fields

### ContentProperty

Identifies the [Content](/opensilver/12330) dependency property.

**Declaration**

[tabgroup]
[tab=C#]
```
public static readonly DependencyProperty ContentProperty
```
[/tab]
[/tabgroup]

**Field Value**

| Type | Description |
|------|-------------|
| DependencyProperty | No description |


### ContentTemplateProperty

Identifies the ContentTemplate dependency property.

**Declaration**

[tabgroup]
[tab=C#]
```
public static readonly DependencyProperty ContentTemplateProperty
```
[/tab]
[/tabgroup]

**Field Value**

| Type | Description |
|------|-------------|
| DependencyProperty | No description |


### ContentTemplateSelectorProperty

Identifies the ContentTemplateSelector dependency property.

**Declaration**

[tabgroup]
[tab=C#]
```
public static readonly DependencyProperty ContentTemplateSelectorProperty
```
[/tab]
[/tabgroup]

**Field Value**

| Type | Description |
|------|-------------|
| DependencyProperty | No description |


## Properties

### Content

Gets or sets the content of a [ContentControl](/opensilver/12090).

**Declaration**

[tabgroup]
[tab=C#]
```
public object Content { get; set; }
```
[/tab]
[/tabgroup]

**Property Value**

| Type | Description |
|------|-------------|
| object | An object that contains the control's content. The default value is null. |


### ContentTemplate

Gets or sets the data template used to display the content of the [ContentControl](/opensilver/12090).

**Declaration**

[tabgroup]
[tab=C#]
```
public DataTemplate ContentTemplate { get; set; }
```
[/tab]
[/tabgroup]

**Property Value**

| Type | Description |
|------|-------------|
| DataTemplate | A data template. The default value is null. |


### ContentTemplateSelector

Gets or sets a template selector that enables an application writer to provide custom template-selection logic.

**Declaration**

[tabgroup]
[tab=C#]
```
public DataTemplateSelector ContentTemplateSelector { get; set; }
```
[/tab]
[/tabgroup]

**Property Value**

| Type | Description |
|------|-------------|
| DataTemplateSelector | A data template selector. The default value is null. |


### LogicalChildren

Gets an enumerator to the content control's logical child elements.

**Declaration**

[tabgroup]
[tab=C#]
```
protected override IEnumerator LogicalChildren { get; }
```
[/tab]
[/tabgroup]

**Property Value**

| Type | Description |
|------|-------------|
| IEnumerator | An enumerator. The default value is null. |


## Methods

### OnContentChanged(object, object)

Called when the [Content](/opensilver/12330) property changes.

**Declaration**

[tabgroup]
[tab=C#]
```
protected virtual void OnContentChanged(object oldContent, object newContent)
```
[/tab]
[/tabgroup]

**Parameters**

| Name | Type | Description |
|------|------|-------------|
| oldContent | object | The old value of the [Content](/opensilver/12330) property. |
| newContent | object | The new value of the [Content](/opensilver/12330) property. |


### OnContentTemplateChanged(DataTemplate, DataTemplate)

Called when the ContentTemplate property changes.

**Declaration**

[tabgroup]
[tab=C#]
```
protected virtual void OnContentTemplateChanged(DataTemplate oldContentTemplate, DataTemplate newContentTemplate)
```
[/tab]
[/tabgroup]

**Parameters**

| Name | Type | Description |
|------|------|-------------|
| oldContentTemplate | DataTemplate | The old value of the ContentTemplate property. |
| newContentTemplate | DataTemplate | The new value of the ContentTemplate property. |


### OnContentTemplateSelectorChanged(DataTemplateSelector, DataTemplateSelector)

Called when the ContentTemplateSelector property changes.

**Declaration**

[tabgroup]
[tab=C#]
```
protected virtual void OnContentTemplateSelectorChanged(DataTemplateSelector oldContentTemplateSelector, DataTemplateSelector newContentTemplateSelector)
```
[/tab]
[/tabgroup]

**Parameters**

| Name | Type | Description |
|------|------|-------------|
| oldContentTemplateSelector | DataTemplateSelector | The old value of the ContentTemplateSelector property. |
| newContentTemplateSelector | DataTemplateSelector | The new value of the ContentTemplateSelector property. |




## Additional Resources
- [OpenSilver Documentation](/opensilver) - Documentation Home
- [Building Your First OpenSilver Project](/opensilver/4165) - Getting Started
- [GitHub Repository](https://github.com/opensilver/opensilver) - Source Code
- [NuGet Package](https://www.nuget.org/packages/OpenSilver) - Package Download
