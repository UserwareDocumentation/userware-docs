# CheckBox Control
OpenSilver에서 CheckBox 컨트롤의 특징과 사용법에 대해 설명합니다. 이 문서는 개발자가 CheckBox 컨트롤을 효과적으로 구현할 수 있도록 필요한 정보를 제공합니다.

## 컨트롤 개요
CheckBox 컨트롤은 OpenSilver 애플리케이션에서 사용자가 참/거짓 또는 선택/비선택 상태를 전환할 수 있는 기본적인 UI 요소입니다. WPF를 비롯한 다양한 XAML 기반 플랫폼에 익숙한 개발자라면 OpenSilver의 CheckBox 컨트롤을 쉽게 활용할 수 있습니다.

## 클래스 정보
CheckBox 컨트롤은 OpenSilver.dll 어셈블리에 포함된 클래스입니다.

[reference=1]
- class: CheckBox
  namespace: System.Windows.Controls
  assembly: OpenSilver.dll
  description: Represents a control that a user can select (check) or clear (uncheck).
[/reference]

자세한 클래스 정의, 상속 구조, 속성, 이벤트, 메서드 등은 [CheckBox 클래스 레퍼런스 문서](https://example.com/checkbox-reference)에서 확인할 수 있습니다.

## 상속 계층 구조
CheckBox 컨트롤의 클래스 상속 계층은 다음과 같습니다.

[hierarchy]
- class: Object
  namespace: System
  level: 1
- class: DependencyObject
  namespace: System.Windows
  level: 2
  parent: Object
- class: UIElement
  namespace: System.Windows
  level: 3
  parent: DependencyObject
- class: FrameworkElement
  namespace: System.Windows
  level: 4
  parent: UIElement
- class: Control
  namespace: System.Windows.Controls
  level: 5
  parent: FrameworkElement
- class: ContentControl
  namespace: System.Windows.Controls
  level: 6
  parent: Control
- class: ButtonBase
  namespace: System.Windows.Controls.Primitives
  level: 7
  parent: ContentControl
- class: ToggleButton
  namespace: System.Windows.Controls.Primitives
  level: 8
  parent: ButtonBase
- class: CheckBox
  namespace: System.Windows.Controls
  level: 9
  parent: ToggleButton
  highlight: true
[/hierarchy]

CheckBox는 ContentControl에서 콘텐츠 호스팅 기능을, ButtonBase에서 클릭 이벤트 처리를, ToggleButton에서 상태 전환 기능을 상속받아 구성됩니다. 이 계층 구조는 WPF와 동일하여 기존 지식을 활용하기에 유리합니다.

## 주요 속성  
CheckBox 컨트롤의 주요 속성은 다음과 같습니다.

| Property (Type)           | Remark                                  | Class           |
|---------------------------|-----------------------------------------|-----------------|
| IsChecked (bool?)         | 체크박스의 선택 상태를 정의              | ToggleButton    |
| IsThreeState (bool)       | 세 가지 상태 지원 여부                   | CheckBox        |
| Content (object)          | 체크박스에 표시할 내용을 정의             | ContentControl  |
| Checked (RoutedEventHandler)| 체크박스가 선택되면 발생하는 이벤트      | ToggleButton    |
| Unchecked (RoutedEventHandler)| 체크박스가 선택 해제되면 발생하는 이벤트 | ToggleButton    |
| Indeterminate (RoutedEventHandler)| 체크박스가 불확정 상태가 되면 발생하는 이벤트 | ToggleButton |
| IsEnabled (bool)          | 체크박스의 활성화/비활성화 상태를 제어     | Control         |

이 속성들은 CheckBox의 동작과 외관을 자유롭게 조정할 수 있게 해주며, 각 속성은 상속 계층에서 특정 클래스로부터 제공됩니다.

# IsChecked 바인딩  
CheckBox의 IsChecked 속성을 활용해 체크박스의 상태를 설정하거나 데이터에 바인딩합니다.

## IsChecked 소스코드  
아래 예제는 CheckBox의 IsChecked 속성을 ViewModel의 프로퍼티에 바인딩하는 방법을 보여줍니다.

[tabgroup]  
[tab=XAML|url=https://github.com/OpenSilver/samples/blob/master/src/OpenSilver.Samples/OSFSample.CheckBoxIsChecked/CheckBoxIsCheckedExample.xaml|text=GitHub: CheckBoxIsCheckedExample.xaml]  
```
<StackPanel HorizontalAlignment="Left">  
    <CheckBox Content="Accept Terms" IsChecked="{Binding IsTermsAccepted, Mode=TwoWay}"/>  
    <Button Content="Continue" IsEnabled="{Binding IsTermsAccepted}" Margin="0,10,0,0"/>  
    <TextBlock Text="{Binding StatusText}" Margin="0,5,0,0"/>  
</StackPanel>  
```
[/tab]  
[tab=C#|url=https://github.com/OpenSilver/samples/blob/master/src/OpenSilver.Samples/OSFSample.CheckBoxIsChecked/CheckBoxIsCheckedExample.xaml.cs|text=GitHub: CheckBoxIsCheckedExample.xaml.cs]  
```
public class CheckBoxViewModel : ViewModelBase  
{  
    private bool _isTermsAccepted;  
    
    public bool IsTermsAccepted  
    {  
        get => _isTermsAccepted;  
        set  
        {  
            if (SetProperty(ref _isTermsAccepted, value))  
            {  
                UpdateStatusText();  
            }  
        }  
    }  
    
    private string _statusText;  
    public string StatusText  
    {  
        get => _statusText;  
        set => SetProperty(ref _statusText, value);  
    }  
    
    public CheckBoxViewModel()  
    {  
        UpdateStatusText();  
    }  
    
    private void UpdateStatusText()  
    {  
        StatusText = IsTermsAccepted ? "Terms accepted, you may continue" : "Please accept terms to continue";  
    }  
}  
```
[/tab]  
[/tabgroup]

OpenSilver는 데이터 바인딩을 통해 IsChecked 속성의 동적인 설정을 지원하며, 이러한 방식은 MVVM 패턴 구현에 유용합니다.

## IsChecked 결과 확인
실행 시 체크박스 선택 여부에 따라 Button의 활성화 상태와 텍스트 메시지가 실시간으로 변경됩니다.

[[[DEMO:CHECKBOX_ISCHECKED]]]

이 예제는 데이터 바인딩을 통해 CheckBox의 상태를 다른 UI 요소와 연동하는 방법을 보여줍니다.

# Checked/Unchecked 이벤트 처리  
CheckBox의 Checked 및 Unchecked 이벤트를 활용해 상태 변경 시 동작을 정의합니다.

## Checked/Unchecked 소스코드  
아래 코드는 체크박스 상태 변경 시 이벤트를 처리하는 예제입니다.

[tabgroup]  
[tab=XAML|url=https://github.com/OpenSilver/samples/blob/master/src/OpenSilver.Samples/OSFSample.CheckBoxEvents/CheckBoxEventsExample.xaml|text=GitHub: CheckBoxEventsExample.xaml]  
```
<StackPanel HorizontalAlignment="Left">  
    <CheckBox x:Name="chkNotify" Content="Send email notifications" 
              Checked="CheckBox_Checked" Unchecked="CheckBox_Unchecked"/>  
    <TextBlock x:Name="txtStatus" Margin="0,10,0,0"/>  
    <Rectangle x:Name="rectIndicator" Width="20" Height="20" 
               Fill="Gray" Margin="0,10,0,0" HorizontalAlignment="Left"/>  
</StackPanel>  
```
[/tab]  
[tab=C#|url=https://github.com/OpenSilver/samples/blob/master/src/OpenSilver.Samples/OSFSample.CheckBoxEvents/CheckBoxEventsExample.xaml.cs|text=GitHub: CheckBoxEventsExample.xaml.cs]  
```
public partial class CheckBoxEventsExample : UserControl  
{  
    public CheckBoxEventsExample()  
    {  
        this.InitializeComponent();  
    }  

    private void CheckBox_Checked(object sender, RoutedEventArgs e)  
    {  
        txtStatus.Text = "Notifications enabled";  
        rectIndicator.Fill = new SolidColorBrush(Colors.Green);  
        MessageBox.Show("You will receive email notifications");  
    }  

    private void CheckBox_Unchecked(object sender, RoutedEventArgs e)  
    {  
        txtStatus.Text = "Notifications disabled";  
        rectIndicator.Fill = new SolidColorBrush(Colors.Red);  
        MessageBox.Show("Email notifications have been turned off");  
    }  
}  
```
[/tab]  
[/tabgroup]

OpenSilver는 Checked/Unchecked 이벤트 처리를 지원하며, 이는 체크박스 상태 변경에 따른 UI 업데이트나 비즈니스 로직 실행에 효과적입니다.

## Checked/Unchecked 결과 확인
체크박스 선택/해제 시 텍스트와 색상 표시기가 업데이트되고 메시지 박스가 나타나며, 이벤트 처리가 제대로 작동함을 볼 수 있습니다.

[[[DEMO:CHECKBOX_EVENTS]]]

Checked/Unchecked 이벤트는 사용자의 선택에 따른 즉각적인 피드백을 제공하는 데 유용합니다.

# 3-State 체크박스  
CheckBox의 IsThreeState 속성을 활용해 3가지 상태(체크, 미체크, 불확정)를 지원하는 체크박스를 구현합니다.

## 3-State 소스코드  
아래 예제는 3-State 체크박스를 구현하고 활용하는 방법을 보여줍니다.

[tabgroup]  
[tab=XAML|url=https://github.com/OpenSilver/samples/blob/master/src/OpenSilver.Samples/OSFSample.CheckBoxThreeState/CheckBoxThreeStateExample.xaml|text=GitHub: CheckBoxThreeStateExample.xaml]  
```
<StackPanel HorizontalAlignment="Left">  
    <TextBlock Text="Parent Selection:" FontWeight="Bold"/>
    <CheckBox x:Name="parentCheckBox" Content="Select All" 
              IsThreeState="True" Checked="ParentCheckBox_CheckedChanged" 
              Unchecked="ParentCheckBox_CheckedChanged" 
              Indeterminate="ParentCheckBox_CheckedChanged"/>  
    
    <TextBlock Text="Child Items:" FontWeight="Bold" Margin="0,10,0,0"/>
    <StackPanel Margin="20,0,0,0">
        <CheckBox x:Name="childCheckBox1" Content="Item 1" 
                  Checked="ChildCheckBox_CheckedChanged" 
                  Unchecked="ChildCheckBox_CheckedChanged"/>  
        <CheckBox x:Name="childCheckBox2" Content="Item 2" 
                  Checked="ChildCheckBox_CheckedChanged" 
                  Unchecked="ChildCheckBox_CheckedChanged"/>  
        <CheckBox x:Name="childCheckBox3" Content="Item 3" 
                  Checked="ChildCheckBox_CheckedChanged" 
                  Unchecked="ChildCheckBox_CheckedChanged"/>  
    </StackPanel>
    
    <TextBlock x:Name="txtStatus" Margin="0,10,0,0"/>  
</StackPanel>  
```
[/tab]  
[tab=C#|url=https://github.com/OpenSilver/samples/blob/master/src/OpenSilver.Samples/OSFSample.CheckBoxThreeState/CheckBoxThreeStateExample.xaml.cs|text=GitHub: CheckBoxThreeStateExample.xaml.cs]  
```
public partial class CheckBoxThreeStateExample : UserControl  
{  
    public CheckBoxThreeStateExample()  
    {  
        this.InitializeComponent();  
    }  

    private void ParentCheckBox_CheckedChanged(object sender, RoutedEventArgs e)  
    {  
        // Modify child checkboxes based on parent state
        bool? isChecked = parentCheckBox.IsChecked;
        
        childCheckBox1.IsChecked = isChecked;
        childCheckBox2.IsChecked = isChecked;
        childCheckBox3.IsChecked = isChecked;
        
        UpdateStatus();
    }  

    private void ChildCheckBox_CheckedChanged(object sender, RoutedEventArgs e)  
    {  
        // Update parent checkbox based on children
        bool allChecked = (childCheckBox1.IsChecked == true) && 
                         (childCheckBox2.IsChecked == true) && 
                         (childCheckBox3.IsChecked == true);
                         
        bool allUnchecked = (childCheckBox1.IsChecked == false) && 
                           (childCheckBox2.IsChecked == false) && 
                           (childCheckBox3.IsChecked == false);
        
        if (allChecked)
        {
            parentCheckBox.IsChecked = true;
        }
        else if (allUnchecked)
        {
            parentCheckBox.IsChecked = false;
        }
        else
        {
            parentCheckBox.IsChecked = null; // Indeterminate state
        }
        
        UpdateStatus();
    }
    
    private void UpdateStatus()
    {
        int checkedCount = 0;
        if (childCheckBox1.IsChecked == true) checkedCount++;
        if (childCheckBox2.IsChecked == true) checkedCount++;
        if (childCheckBox3.IsChecked == true) checkedCount++;
        
        txtStatus.Text = $"Selected items: {checkedCount} of 3";
    }
}  
```
[/tab]  
[/tabgroup]

OpenSilver는 IsThreeState 속성을 통해 불확정 상태를 포함한 3-State 체크박스를 지원하며, 이는 다중 항목 선택 UI에 유용합니다.

## 3-State 결과 확인
부모 체크박스 상태에 따라 모든 자식 체크박스가 업데이트되고, 자식 체크박스 상태에 따라 부모 체크박스가 체크, 미체크 또는 불확정 상태로 변경됩니다.

[[[DEMO:CHECKBOX_THREESTATE]]]

3-State 체크박스는 계층적 데이터 구조에서의 선택 상태를 시각적으로 표현하는데 효과적입니다.

# 그룹 컨트롤  
CheckBox 컨트롤을 그룹으로 구성하여 관련 옵션을 함께 관리합니다.

## 그룹 컨트롤 소스코드  
아래 예제는 체크박스 그룹을 사용하여 다중 선택 옵션을 구현하는 방법을 보여줍니다.

[tabgroup]  
[tab=XAML|url=https://github.com/OpenSilver/samples/blob/master/src/OpenSilver.Samples/OSFSample.CheckBoxGroup/CheckBoxGroupExample.xaml|text=GitHub: CheckBoxGroupExample.xaml]  
```
<StackPanel HorizontalAlignment="Left">  
    <TextBlock Text="Select notification methods:" FontWeight="Bold"/>
    <GroupBox Header="Notification Options" Margin="0,5,0,0">
        <StackPanel Margin="5">
            <CheckBox x:Name="chkEmail" Content="Email" 
                      Checked="NotificationOption_Changed"
                      Unchecked="NotificationOption_Changed"/>  
            <CheckBox x:Name="chkSMS" Content="SMS" 
                      Checked="NotificationOption_Changed"
                      Unchecked="NotificationOption_Changed"/>  
            <CheckBox x:Name="chkPush" Content="Push Notification" 
                      Checked="NotificationOption_Changed"
                      Unchecked="NotificationOption_Changed"/>  
            <CheckBox x:Name="chkInApp" Content="In-App Message" 
                      Checked="NotificationOption_Changed"
                      Unchecked="NotificationOption_Changed"/>  
        </StackPanel>
    </GroupBox>
    
    <TextBlock Text="Summary:" FontWeight="Bold" Margin="0,10,0,0"/>
    <TextBlock x:Name="txtSummary" TextWrapping="Wrap"/>
    
    <Button x:Name="btnSave" Content="Save Preferences" 
            Margin="0,10,0,0" Click="BtnSave_Click"/>
</StackPanel>  
```
[/tab]  
[tab=C#|url=https://github.com/OpenSilver/samples/blob/master/src/OpenSilver.Samples/OSFSample.CheckBoxGroup/CheckBoxGroupExample.xaml.cs|text=GitHub: CheckBoxGroupExample.xaml.cs]  
```
public partial class CheckBoxGroupExample : UserControl  
{  
    public CheckBoxGroupExample()  
    {  
        this.InitializeComponent();  
        UpdateSummary();
    }  

    private void NotificationOption_Changed(object sender, RoutedEventArgs e)  
    {  
        UpdateSummary();
    }
    
    private void UpdateSummary()
    {
        List<string> selectedOptions = new List<string>();
        
        if (chkEmail.IsChecked == true) selectedOptions.Add("Email");
        if (chkSMS.IsChecked == true) selectedOptions.Add("SMS");
        if (chkPush.IsChecked == true) selectedOptions.Add("Push");
        if (chkInApp.IsChecked == true) selectedOptions.Add("In-App");
        
        if (selectedOptions.Count > 0)
        {
            txtSummary.Text = $"You will receive notifications via: {string.Join(", ", selectedOptions)}";
            btnSave.IsEnabled = true;
        }
        else
        {
            txtSummary.Text = "No notification methods selected";
            btnSave.IsEnabled = false;
        }
    }
    
    private void BtnSave_Click(object sender, RoutedEventArgs e)
    {
        MessageBox.Show("Notification preferences saved successfully!");
    }
}  
```
[/tab]  
[/tabgroup]

OpenSilver는 체크박스 그룹 구성을 지원하여 관련 옵션을 효과적으로 관리할 수 있으며, 사용자 선택에 따른 UI 업데이트가 가능합니다.

## 그룹 컨트롤 결과 확인
체크박스 선택에 따라 요약 정보가 실시간으로 업데이트되며, 최소 하나의 옵션이 선택되어야 저장 버튼이 활성화됩니다.

[[[DEMO:CHECKBOX_GROUP]]]

체크박스 그룹은 사용자에게 다중 선택 옵션을 제공하고 선택 사항을 효과적으로 관리하는 데 유용합니다.

# 정리하며  
OpenSilver의 CheckBox 컨트롤은 IsChecked 바인딩, Checked/Unchecked 이벤트, 3-State 기능, 그룹 컨트롤 구성 등 핵심 기능을 제공합니다. WPF와 유사한 구조를 기반으로 하여, XAML에 익숙한 개발자라면 기존 지식을 활용해 효율적이고 유연한 UI를 구현할 수 있습니다.

이 문서에서 다룬 예제들은 OpenSilver의 강력한 상호작용 기능을 보여주며, 실제 애플리케이션에서 다양한 요구사항을 충족할 수 있는 유연성을 입증합니다. 데이터 바인딩과 이벤트 처리를 결합하면 복잡한 사용자 인터페이스도 깔끔하게 관리할 수 있고, 3-State 기능과 그룹 컨트롤을 활용하면 사용자 경험을 한층 더 개선할 수 있습니다.

OpenSilver는 CheckBox 컨트롤을 통해 ToggleButton 기반의 XAML 설계를 그대로 지원하며, 이를 웹 환경에서도 네이티브 수준으로 구현할 수 있는 플랫폼으로서의 강점을 드러냅니다. 이러한 특성은 데스크톱, MAUI와 같은 크로스플랫폼 XAML 개발 환경에서의 경험을 자연스럽게 연결하며, 다양한 플랫폼에서 일관된 UI 설계를 가능하게 하는 기반을 제공합니다.