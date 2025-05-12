# Grid Control
OpenSilver에서 Grid 컨트롤의 특징과 사용법에 대해 설명합니다. 이 문서는 개발자가 Grid 컨트롤을 효과적으로 구현할 수 있도록 필요한 정보를 제공합니다.

## 컨트롤 개요
Grid 컨트롤은 OpenSilver 애플리케이션에서 행과 열을 이용한 테이블 형태의 레이아웃을 구성할 수 있는 패널 컨트롤입니다. 유연한 크기 조정과 복잡한 레이아웃 설계를 가능하게 하며, WPF를 비롯한 다양한 XAML 기반 플랫폼에 익숙한 개발자라면 OpenSilver의 Grid 컨트롤을 쉽게 활용할 수 있습니다.

## 클래스 정보
Grid 컨트롤은 OpenSilver.dll 어셈블리에 포함된 클래스입니다.

[reference=1]
- class: Grid
  namespace: System.Windows.Controls
  assembly: OpenSilver.dll
  description: Defines a flexible grid area that consists of columns and rows.
  url: /opensilver/12100
[/reference]

자세한 클래스 정의, 상속 구조, 속성, 이벤트, 메서드 등은 [Grid 클래스 레퍼런스 문서](https://example.com/grid-reference)에서 확인할 수 있습니다.

## 상속 계층 구조
Grid 컨트롤의 클래스 상속 계층은 다음과 같습니다.

[hierarchy]
- class: Object
  namespace: System
  level: 1
- class: DispatcherObject
  namespace: System.Windows.Threading
  level: 2
  parent: Object
  url: /opensilver/de/12648
- class: DependencyObject
  namespace: System.Windows
  level: 3
  parent: DispatcherObject
  url: /opensilver/de/11834
- class: UIElement
  namespace: System.Windows
  level: 4
  parent: DependencyObject
  url: /opensilver/de/11957
- class: FrameworkElement
  namespace: System.Windows
  level: 5
  parent: UIElement
  url: /opensilver/de/11875
- class: Control
  namespace: System.Windows.Controls
  level: 6
  parent: FrameworkElement
  url: /opensilver/de/12096
- class: ContentControl
  namespace: System.Windows.Controls
  level: 7
  parent: Control
  url: /opensilver/de/12090
- class: ButtonBase
  namespace: System.Windows.Controls.Primitives
  level: 8
  parent: ContentControl
  url: /opensilver/de/12169
- class: Button
  namespace: System.Windows.Controls
  level: 9
  parent: ButtonBase
  url: /opensilver/de/12077
  highlight: true
[/hierarchy]

Grid는 Panel 클래스를 상속받아 자식 요소 배치 기능을 제공하며, RowDefinitions와 ColumnDefinitions를 통해 행과 열 기반의 레이아웃을 구현합니다. 이 계층 구조는 WPF와 동일하여 기존 지식을 활용하기에 유리합니다.

## 주요 속성  
Grid 컨트롤의 주요 속성은 다음과 같습니다.

| Property (Type)                      | Remark                                          | Class           |
|--------------------------------------|--------------------------------------------------|-----------------|
| RowDefinitions (RowDefinitionCollection) | 그리드의 행을 정의하는 컬렉션                   | Grid            |
| ColumnDefinitions (ColumnDefinitionCollection) | 그리드의 열을 정의하는 컬렉션             | Grid            |
| Grid.Row (int)                       | 자식 요소가 위치할 행 인덱스를 설정(첨부 속성)     | Grid            |
| Grid.Column (int)                    | 자식 요소가 위치할 열 인덱스를 설정(첨부 속성)     | Grid            |
| Grid.RowSpan (int)                   | 자식 요소가 차지할 행의 개수를 설정(첨부 속성)     | Grid            |
| Grid.ColumnSpan (int)                | 자식 요소가 차지할 열의 개수를 설정(첨부 속성)     | Grid            |
| ShowGridLines (bool)                 | 그리드 라인 표시 여부 설정                        | Grid            |
| Background (Brush)                   | 그리드의 배경색을 설정                           | Panel           |

이 속성들은 Grid의 구조와 레이아웃을 자유롭게 조정할 수 있게 해주며, 각 속성은 상속 계층에서 특정 클래스로부터 제공됩니다.

# 기본 사용법  
Grid의 기본적인 사용 방법과 행/열 정의 방법을 알아봅니다.

## 기본 소스코드  
아래 예제는 Grid를 사용하여 기본적인 레이아웃을 구성하는 방법을 보여줍니다.

[tabgroup]  
[tab=XAML|url=https://github.com/OpenSilver/samples/blob/master/src/OpenSilver.Samples/OSFSample.GridBasic/GridBasicExample.xaml|text=GitHub: GridBasicExample.xaml]  
```
<StackPanel HorizontalAlignment="Left">
    <TextBlock Text="Basic Grid Layout (3x3)" 
               FontWeight="Bold" 
               Margin="0,0,0,10"/>
    
    <Grid Width="300" 
          Height="300" 
          Background="#F0F0F0" 
          ShowGridLines="True">
        <!-- 행 정의 -->
        <Grid.RowDefinitions>
            <RowDefinition Height="*"/>
            <RowDefinition Height="*"/>
            <RowDefinition Height="*"/>
        </Grid.RowDefinitions>
        
        <!-- 열 정의 -->
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="*"/>
            <ColumnDefinition Width="*"/>
            <ColumnDefinition Width="*"/>
        </Grid.ColumnDefinitions>
        
        <!-- 셀 내용 -->
        <Border Grid.Row="0" Grid.Column="0" Background="#FF5722" Margin="5">
            <TextBlock Text="Row 0, Col 0" HorizontalAlignment="Center" VerticalAlignment="Center" Foreground="White"/>
        </Border>
        
        <Border Grid.Row="0" Grid.Column="1" Background="#4CAF50" Margin="5">
            <TextBlock Text="Row 0, Col 1" HorizontalAlignment="Center" VerticalAlignment="Center" Foreground="White"/>
        </Border>
        
        <Border Grid.Row="0" Grid.Column="2" Background="#2196F3" Margin="5">
            <TextBlock Text="Row 0, Col 2" HorizontalAlignment="Center" VerticalAlignment="Center" Foreground="White"/>
        </Border>
        
        <Border Grid.Row="1" Grid.Column="0" Background="#9C27B0" Margin="5">
            <TextBlock Text="Row 1, Col 0" HorizontalAlignment="Center" VerticalAlignment="Center" Foreground="White"/>
        </Border>
        
        <Border Grid.Row="1" Grid.Column="1" Background="#FFC107" Margin="5">
            <TextBlock Text="Row 1, Col 1" HorizontalAlignment="Center" VerticalAlignment="Center"/>
        </Border>
        
        <Border Grid.Row="1" Grid.Column="2" Background="#795548" Margin="5">
            <TextBlock Text="Row 1, Col 2" HorizontalAlignment="Center" VerticalAlignment="Center" Foreground="White"/>
        </Border>
        
        <Border Grid.Row="2" Grid.Column="0" Background="#607D8B" Margin="5">
            <TextBlock Text="Row 2, Col 0" HorizontalAlignment="Center" VerticalAlignment="Center" Foreground="White"/>
        </Border>
        
        <Border Grid.Row="2" Grid.Column="1" Background="#E91E63" Margin="5">
            <TextBlock Text="Row 2, Col 1" HorizontalAlignment="Center" VerticalAlignment="Center" Foreground="White"/>
        </Border>
        
        <Border Grid.Row="2" Grid.Column="2" Background="#009688" Margin="5">
            <TextBlock Text="Row 2, Col 2" HorizontalAlignment="Center" VerticalAlignment="Center" Foreground="White"/>
        </Border>
    </Grid>
    
    <TextBlock Text="Properties:" 
               FontWeight="Bold" 
               Margin="0,20,0,5"/>
               
    <TextBlock Text="• Each cell shows its Row and Column index" Margin="10,0,0,3"/>
    <TextBlock Text="• ShowGridLines=True to display grid lines" Margin="10,0,0,3"/>
    <TextBlock Text="• All rows and columns use equal sizing (*)" Margin="10,0,0,3"/>
    <TextBlock Text="• Each cell has a 5px margin for spacing" Margin="10,0,0,3"/>
</StackPanel>  
```
[/tab]  
[tab=C#|url=https://github.com/OpenSilver/samples/blob/master/src/OpenSilver.Samples/OSFSample.GridBasic/GridBasicExample.xaml.cs|text=GitHub: GridBasicExample.xaml.cs]  
```
public partial class GridBasicExample : UserControl  
{  
    public GridBasicExample()  
    {  
        this.InitializeComponent();  
    }  
}  
```
[/tab]  
[/tabgroup]

OpenSilver는 Grid 컨트롤에서 RowDefinitions와 ColumnDefinitions를 통해 행과 열을 정의하며, Grid.Row와 Grid.Column 첨부 속성을 사용하여 자식 요소의 위치를 지정할 수 있습니다.

## 기본 결과 확인
행과 열이 각각 3개씩 정의된 3x3 그리드가 생성되고, 각 셀에는 해당 위치를 나타내는 텍스트가 표시됩니다. 그리드 라인이 표시되어 각 셀의 경계를 시각적으로 확인할 수 있습니다.

[[[DEMO:GRID_BASIC]]]

이 예제는 Grid의 기본 사용법과 행/열 정의 방법을 보여줍니다.

# 크기 설정  
Grid의 행과 열 크기를 다양한 방식으로 설정하는 방법을 알아봅니다.

## 크기 설정 소스코드  
아래 예제는 다양한 크기 단위를 사용하여 Grid의 행과 열 크기를 설정하는 방법을 보여줍니다.

[tabgroup]  
[tab=XAML|url=https://github.com/OpenSilver/samples/blob/master/src/OpenSilver.Samples/OSFSample.GridSizing/GridSizingExample.xaml|text=GitHub: GridSizingExample.xaml]  
```
<StackPanel HorizontalAlignment="Left">
    <TextBlock Text="Grid Sizing Options" 
               FontWeight="Bold" 
               Margin="0,0,0,10"/>
    
    <Grid Width="400" 
          Height="300" 
          Background="#F0F0F0" 
          ShowGridLines="True">
        <!-- 행 정의 - 다양한 크기 단위 사용 -->
        <Grid.RowDefinitions>
            <RowDefinition Height="Auto"/>       <!-- 컨텐츠에 맞게 자동 크기 조정 -->
            <RowDefinition Height="50"/>         <!-- 고정 크기 (픽셀) -->
            <RowDefinition Height="*"/>          <!-- 나머지 공간의 1배 -->
            <RowDefinition Height="2*"/>         <!-- 나머지 공간의 2배 -->
        </Grid.RowDefinitions>
        
        <!-- 열 정의 - 다양한 크기 단위 사용 -->
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="100"/>      <!-- 고정 크기 (픽셀) -->
            <ColumnDefinition Width="Auto"/>     <!-- 컨텐츠에 맞게 자동 크기 조정 -->
            <ColumnDefinition Width="*"/>        <!-- 나머지 공간 모두 사용 -->
        </Grid.ColumnDefinitions>
        
        <!-- 행(Row) 설명 -->
        <Border Grid.Row="0" Grid.Column="0" Background="#BBDEFB" Margin="2">
            <TextBlock Text="Auto Height" HorizontalAlignment="Center" VerticalAlignment="Center"/>
        </Border>
        
        <Border Grid.Row="1" Grid.Column="0" Background="#BBDEFB" Margin="2">
            <TextBlock Text="50px Height" HorizontalAlignment="Center" VerticalAlignment="Center"/>
        </Border>
        
        <Border Grid.Row="2" Grid.Column="0" Background="#BBDEFB" Margin="2">
            <TextBlock Text="1* Height" HorizontalAlignment="Center" VerticalAlignment="Center"/>
        </Border>
        
        <Border Grid.Row="3" Grid.Column="0" Background="#BBDEFB" Margin="2">
            <TextBlock Text="2* Height" HorizontalAlignment="Center" VerticalAlignment="Center"/>
        </Border>
        
        <!-- 열(Column) 설명 -->
        <Border Grid.Row="0" Grid.Column="1" Background="#C8E6C9" Margin="2">
            <TextBlock Text="Auto Width" HorizontalAlignment="Center" VerticalAlignment="Center"/>
        </Border>
        
        <Border Grid.Row="0" Grid.Column="2" Background="#FFECB3" Margin="2">
            <TextBlock Text="* Width (Remaining Space)" HorizontalAlignment="Center" VerticalAlignment="Center"/>
        </Border>
        
        <!-- 셀 내용 -->
        <Border Grid.Row="1" Grid.Column="1" Background="#C8E6C9" Margin="2">
            <TextBlock Text="This content determines width" HorizontalAlignment="Center" VerticalAlignment="Center"/>
        </Border>
        
        <Border Grid.Row="1" Grid.Column="2" Background="#FFECB3" Margin="2">
            <TextBlock Text="Fills Remaining Width" HorizontalAlignment="Center" VerticalAlignment="Center"/>
        </Border>
        
        <Border Grid.Row="2" Grid.Column="1" Background="#C8E6C9" Margin="2">
            <StackPanel Orientation="Vertical" HorizontalAlignment="Center" VerticalAlignment="Center">
                <TextBlock Text="Auto adjusts" HorizontalAlignment="Center"/>
                <TextBlock Text="to content" HorizontalAlignment="Center"/>
            </StackPanel>
        </Border>
        
        <Border Grid.Row="2" Grid.Column="2" Background="#FFECB3" Margin="2">
            <TextBlock Text="* (1x Share)" HorizontalAlignment="Center" VerticalAlignment="Center"/>
        </Border>
        
        <Border Grid.Row="3" Grid.Column="1" Grid.ColumnSpan="2" Background="#F8BBD0" Margin="2">
            <TextBlock Text="ColumnSpan=2 (Spans Auto + * Columns)" HorizontalAlignment="Center" VerticalAlignment="Center"/>
        </Border>
    </Grid>
    
    <TextBlock Text="Size Types:" 
               FontWeight="Bold" 
               Margin="0,20,0,5"/>
               
    <TextBlock Text="• Auto: Sizes to content" Margin="10,0,0,3"/>
    <TextBlock Text="• Pixel (e.g., 50px): Fixed size" Margin="10,0,0,3"/>
    <TextBlock Text="• Star (*): Proportional sizing" Margin="10,0,0,3"/>
    <TextBlock Text="• Multiple Star (e.g., 2*): Takes multiple proportion of available space" Margin="10,0,0,3"/>
</StackPanel>  
```
[/tab]  
[tab=C#|url=https://github.com/OpenSilver/samples/blob/master/src/OpenSilver.Samples/OSFSample.GridSizing/GridSizingExample.xaml.cs|text=GitHub: GridSizingExample.xaml.cs]  
```
public partial class GridSizingExample : UserControl  
{  
    public GridSizingExample()  
    {  
        this.InitializeComponent();  
    }  
}  
```
[/tab]  
[/tabgroup]

OpenSilver의 Grid 컨트롤은 행과 열 크기를 설정하는 데 Auto, 고정 픽셀, 비례 크기(*)와 같은 다양한 단위를 지원합니다.

## 크기 설정 결과 확인
다양한 크기 단위가 적용된 그리드가 표시되며, Auto 크기는 내용에 맞게 조정되고, 고정 크기는 지정된 픽셀 값을 유지하며, 비례 크기(*)는 가용 공간을 비율에 따라 분배합니다.

[[[DEMO:GRID_SIZING]]]

이 예제는 Grid의 다양한 크기 설정 옵션과 그 효과를 보여줍니다.

# 셀 병합  
Grid에서 Grid.RowSpan과 Grid.ColumnSpan을 활용하여 셀을 병합하는 방법을 알아봅니다.

## 셀 병합 소스코드  
아래 예제는 행과 열을 병합하여 다양한 레이아웃을 구성하는 방법을 보여줍니다.

[tabgroup]  
[tab=XAML|url=https://github.com/OpenSilver/samples/blob/master/src/OpenSilver.Samples/OSFSample.GridSpanning/GridSpanningExample.xaml|text=GitHub: GridSpanningExample.xaml]  
```
<StackPanel HorizontalAlignment="Left">
    <TextBlock Text="Cell Spanning in Grid" 
               FontWeight="Bold" 
               Margin="0,0,0,10"/>
    
    <Grid Width="400" 
          Height="400" 
          Background="#F0F0F0" 
          ShowGridLines="True">
        <!-- 행 정의 -->
        <Grid.RowDefinitions>
            <RowDefinition Height="60"/>
            <RowDefinition Height="*"/>
            <RowDefinition Height="*"/>
            <RowDefinition Height="*"/>
            <RowDefinition Height="60"/>
        </Grid.RowDefinitions>
        
        <!-- 열 정의 -->
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="100"/>
            <ColumnDefinition Width="*"/>
            <ColumnDefinition Width="*"/>
            <ColumnDefinition Width="100"/>
        </Grid.ColumnDefinitions>
        
        <!-- 헤더 (열 병합) -->
        <Border Grid.Row="0" Grid.Column="0" Grid.ColumnSpan="4" Background="#3F51B5" Margin="3">
            <TextBlock Text="Header (ColumnSpan=4)" 
                       FontSize="18" 
                       Foreground="White" 
                       HorizontalAlignment="Center" 
                       VerticalAlignment="Center"/>
        </Border>
        
        <!-- 사이드바 (행 병합) -->
        <Border Grid.Row="1" Grid.Column="0" Grid.RowSpan="3" Background="#FF5722" Margin="3">
            <TextBlock Text="Sidebar (RowSpan=3)" 
                       Foreground="White" 
                       HorizontalAlignment="Center" 
                       VerticalAlignment="Center">
                <TextBlock.RenderTransform>
                    <RotateTransform Angle="270"/>
                </TextBlock.RenderTransform>
            </TextBlock>
        </Border>
        
        <!-- 오른쪽 사이드바 (행 병합) -->
        <Border Grid.Row="1" Grid.Column="3" Grid.RowSpan="3" Background="#FF5722" Margin="3">
            <TextBlock Text="Sidebar (RowSpan=3)" 
                       Foreground="White" 
                       HorizontalAlignment="Center" 
                       VerticalAlignment="Center">
                <TextBlock.RenderTransform>
                    <RotateTransform Angle="90"/>
                </TextBlock.RenderTransform>
            </TextBlock>
        </Border>
        
        <!-- 메인 콘텐츠 영역 (행+열 병합) -->
        <Border Grid.Row="1" Grid.Column="1" Grid.RowSpan="2" Grid.ColumnSpan="2" Background="#4CAF50" Margin="3">
            <TextBlock Text="Main Content Area (RowSpan=2, ColumnSpan=2)" 
                       Foreground="White" 
                       HorizontalAlignment="Center" 
                       VerticalAlignment="Center"
                       TextWrapping="Wrap"
                       TextAlignment="Center"/>
        </Border>
        
        <!-- 하단 콘텐츠 영역 (열 병합) -->
        <Border Grid.Row="3" Grid.Column="1" Grid.ColumnSpan="2" Background="#2196F3" Margin="3">
            <TextBlock Text="Bottom Content (ColumnSpan=2)" 
                       Foreground="White" 
                       HorizontalAlignment="Center" 
                       VerticalAlignment="Center"/>
        </Border>
        
        <!-- 푸터 (열 병합) -->
        <Border Grid.Row="4" Grid.Column="0" Grid.ColumnSpan="4" Background="#673AB7" Margin="3">
            <TextBlock Text="Footer (ColumnSpan=4)" 
                       FontSize="18" 
                       Foreground="White" 
                       HorizontalAlignment="Center" 
                       VerticalAlignment="Center"/>
        </Border>
    </Grid>
    
    <TextBlock Text="Spanning Properties:" 
               FontWeight="Bold" 
               Margin="0,20,0,5"/>
               
    <TextBlock Text="• Grid.RowSpan: Spans multiple rows (vertical merging)" Margin="10,0,0,3"/>
    <TextBlock Text="• Grid.ColumnSpan: Spans multiple columns (horizontal merging)" Margin="10,0,0,3"/>
    <TextBlock Text="• Combining RowSpan and ColumnSpan creates larger merged areas" Margin="10,0,0,3"/>
    <TextBlock Text="• ShowGridLines visualizes the grid structure even with spanning" Margin="10,0,0,3"/>
</StackPanel>  
```
[/tab]  
[tab=C#|url=https://github.com/OpenSilver/samples/blob/master/src/OpenSilver.Samples/OSFSample.GridSpanning/GridSpanningExample.xaml.cs|text=GitHub: GridSpanningExample.xaml.cs]  
```
public partial class GridSpanningExample : UserControl  
{  
    public GridSpanningExample()  
    {  
        this.InitializeComponent();  
    }  
}  
```
[/tab]  
[/tabgroup]

OpenSilver는 Grid 컨트롤에서 Grid.RowSpan과 Grid.ColumnSpan 첨부 속성을 사용하여 여러 행과 열을 병합할 수 있으며, 이를 통해 복잡한 레이아웃을 구성할 수 있습니다.

## 셀 병합 결과 확인
다양한 셀 병합이 적용된 그리드가 표시되며, 헤더와 푸터는 모든 열을 병합하고, 사이드바는 여러 행을 병합하며, 메인 콘텐츠 영역은 행과 열을 모두 병합하여 구성된 복합적인 레이아웃을 보여줍니다.

[[[DEMO:GRID_SPANNING]]]

이 예제는 Grid.RowSpan과 Grid.ColumnSpan을 활용한 셀 병합 방법과 복잡한 레이아웃 구성 기법을 보여줍니다.

# 중첩 그리드  
Grid 안에 다른 Grid를 배치하여 복잡한 레이아웃을 구성하는 방법을 알아봅니다.

## 중첩 그리드 소스코드  
아래 예제는 Grid를 중첩하여 복잡한 레이아웃을 구성하는 방법을 보여줍니다.

[tabgroup]  
[tab=XAML|url=https://github.com/OpenSilver/samples/blob/master/src/OpenSilver.Samples/OSFSample.GridNesting/GridNestingExample.xaml|text=GitHub: GridNestingExample.xaml]  
```
<StackPanel HorizontalAlignment="Left">
    <TextBlock Text="Nested Grids" 
               FontWeight="Bold" 
               Margin="0,0,0,10"/>
    
    <!-- 메인 그리드 -->
    <Grid Width="450" 
          Height="450" 
          Background="#EEEEEE">
        <!-- 행 정의 -->
        <Grid.RowDefinitions>
            <RowDefinition Height="Auto"/>
            <RowDefinition Height="*"/>
            <RowDefinition Height="Auto"/>
        </Grid.RowDefinitions>
        
        <!-- 헤더 -->
        <Border Grid.Row="0" Background="#3F51B5" Padding="10">
            <TextBlock Text="Dashboard Layout with Nested Grids" 
                       Foreground="White" 
                       FontSize="18" 
                       HorizontalAlignment="Center"/>
        </Border>
        
        <!-- 콘텐츠 영역 (중첩 그리드) -->
        <Grid Grid.Row="1" Margin="10">
            <Grid.ColumnDefinitions>
                <ColumnDefinition Width="3*"/>
                <ColumnDefinition Width="2*"/>
            </Grid.ColumnDefinitions>
            <Grid.RowDefinitions>
                <RowDefinition Height="*"/>
                <RowDefinition Height="*"/>
            </Grid.RowDefinitions>
            
            <!-- 메인 콘텐츠 영역 (왼쪽 상단) -->
            <Border Grid.Row="0" Grid.Column="0" Background="White" Margin="0,0,5,5" CornerRadius="4">
                <Grid Margin="10">
                    <Grid.RowDefinitions>
                        <RowDefinition Height="Auto"/>
                        <RowDefinition Height="*"/>
                    </Grid.RowDefinitions>
                    
                    <TextBlock Grid.Row="0" Text="Main Content" FontWeight="Bold" Margin="0,0,0,10"/>
                    
                    <!-- 더 깊은 중첩 그리드 (3x2) -->
                    <Grid Grid.Row="1">
                        <Grid.RowDefinitions>
                            <RowDefinition Height="*"/>
                            <RowDefinition Height="*"/>
                            <RowDefinition Height="*"/>
                        </Grid.RowDefinitions>
                        <Grid.ColumnDefinitions>
                            <ColumnDefinition Width="*"/>
                            <ColumnDefinition Width="*"/>
                        </Grid.ColumnDefinitions>
                        
                        <Border Grid.Row="0" Grid.Column="0" Background="#E3F2FD" Margin="2" Padding="5">
                            <TextBlock Text="Item 1" VerticalAlignment="Center" HorizontalAlignment="Center"/>
                        </Border>
                        <Border Grid.Row="0" Grid.Column="1" Background="#E3F2FD" Margin="2" Padding="5">
                            <TextBlock Text="Item 2" VerticalAlignment="Center" HorizontalAlignment="Center"/>
                        </Border>
                        <Border Grid.Row="1" Grid.Column="0" Background="#E3F2FD" Margin="2" Padding="5">
                            <TextBlock Text="Item 3" VerticalAlignment="Center" HorizontalAlignment="Center"/>
                        </Border>
                        <Border Grid.Row="1" Grid.Column="1" Background="#E3F2FD" Margin="2" Padding="5">
                            <TextBlock Text="Item 4" VerticalAlignment="Center" HorizontalAlignment="Center"/>
                        </Border>
                        <Border Grid.Row="2" Grid.Column="0" Background="#E3F2FD" Margin="2" Padding="5">
                            <TextBlock Text="Item 5" VerticalAlignment="Center" HorizontalAlignment="Center"/>
                        </Border>
                        <Border Grid.Row="2" Grid.Column="1" Background="#E3F2FD" Margin="2" Padding="5">
                            <TextBlock Text="Item 6" VerticalAlignment="Center" HorizontalAlignment="Center"/>
                        </Border>
                    </Grid>
                </Grid>
            </Border>
            
            <!-- 사이드 콘텐츠 (오른쪽 상단) -->
            <Border Grid.Row="0" Grid.Column="1" Background="White" Margin="5,0,0,5" CornerRadius="4">
                <Grid Margin="10">
                    <Grid.RowDefinitions>
                        <RowDefinition Height="Auto"/>
                        <RowDefinition Height="*"/>
                    </Grid.RowDefinitions>
                    
                    <TextBlock Grid.Row="0" Text="Side Content" FontWeight="Bold" Margin="0,0,0,10"/>
                    
                    <!-- 중첩된 스택 레이아웃 -->
                    <StackPanel Grid.Row="1">
                        <Border Background="#FFF3E0" Margin="0,0,0,5" Padding="8">
                            <TextBlock Text="Notification 1" VerticalAlignment="Center"/>
                        </Border>
                        <Border Background="#FFF3E0" Margin="0,0,0,5" Padding="8">
                            <TextBlock Text="Notification 2" VerticalAlignment="Center"/>
                        </Border>
                        <Border Background="#FFF3E0" Margin="0,0,0,5" Padding="8">
                            <TextBlock Text="Notification 3" VerticalAlignment="Center"/>
                        </Border>
                    </StackPanel>
                </Grid>
            </Border>
            
            <!-- 하단 콘텐츠 (왼쪽 하단) -->
            <Border Grid.Row="1" Grid.Column="0" Background="White" Margin="0,5,5,0" CornerRadius="4">
                <Grid Margin="10">
                    <Grid.RowDefinitions>
                        <RowDefinition Height="Auto"/>
                        <RowDefinition Height="*"/>
                    </Grid.RowDefinitions>
                    
                    <TextBlock Grid.Row="0" Text="Data Summary" FontWeight="Bold" Margin="0,0,0,10"/>
                    
                    <!-- 또 다른 중첩 그리드 -->
                    <Grid Grid.Row="1">
                        <Grid.ColumnDefinitions>
                            <ColumnDefinition Width="Auto"/>
                            <ColumnDefinition Width="*"/>
                        </Grid.ColumnDefinitions>
                        <Grid.RowDefinitions>
                            <RowDefinition Height="Auto"/>
                            <RowDefinition Height="Auto"/>
                            <RowDefinition Height="Auto"/>
                        </Grid.RowDefinitions>
                        
                        <TextBlock Grid.Row="0" Grid.Column="0" Text="Total Items:" Margin="0,0,10,5" FontWeight="SemiBold"/>
                        <TextBlock Grid.Row="0" Grid.Column="1" Text="105" Margin="0,0,0,5"/>
                        
                        <TextBlock Grid.Row="1" Grid.Column="0" Text="Completed:" Margin="0,0,10,5" FontWeight="SemiBold"/>
                        <TextBlock Grid.Row="1" Grid.Column="1" Text="67" Margin="0,0,0,5"/>
                        
                        <TextBlock Grid.Row="2" Grid.Column="0" Text="Pending:" Margin="0,0,10,5" FontWeight="SemiBold"/>
                        <TextBlock Grid.Row="2" Grid.Column="1" Text="38" Margin="0,0,0,5"/>
                    </Grid>
                </Grid>
            </Border>
            
            <!-- 하단 오른쪽 콘텐츠 -->
            <Border Grid.Row="1" Grid.Column="1" Background="White" Margin="5,5,0,0" CornerRadius="4">
                <Grid Margin="10">
                    <Grid.RowDefinitions>
                        <RowDefinition Height="Auto"/>
                        <RowDefinition Height="*"/>
                    </Grid.RowDefinitions>
                    
                    <TextBlock Grid.Row="0" Text="Quick Actions" FontWeight="Bold" Margin="0,0,0,10"/>
                    
                    <!-- 버튼 그리드 -->
                    <Grid Grid.Row="1">
                        <Grid.RowDefinitions>
                            <RowDefinition Height="*"/>
                            <RowDefinition Height="*"/>
                        </Grid.RowDefinitions>
                        <Grid.ColumnDefinitions>
                            <ColumnDefinition Width="*"/>
                            <ColumnDefinition Width="*"/>
                        </Grid.ColumnDefinitions>
                        
                        <Button Grid.Row="0" Grid.Column="0" Content="Add New" Margin="0,0,2,2"/>
                        <Button Grid.Row="0" Grid.Column="1" Content="Refresh" Margin="2,0,0,2"/>
                        <Button Grid.Row="1" Grid.Column="0" Content="Export" Margin="0,2,2,0"/>
                        <Button Grid.Row="1" Grid.Column="1" Content="Settings" Margin="2,2,0,0"/>
                    </Grid>
                </Grid>
            </Border>
        </Grid>
        
        <!-- 푸터 -->
        <Border Grid.Row="2" Background="#3F51B5" Padding="10">
            <TextBlock Text="Footer Section" 
                       Foreground="White" 
                       HorizontalAlignment="Center"/>
        </Border>
    </Grid>
    
    <TextBlock Text="Nested Grid Benefits:" 
               FontWeight="Bold" 
               Margin="0,20,0,5"/>
               
    <TextBlock Text="• Complex layouts can be created by nesting grids" Margin="10,0,0,3"/>
    <TextBlock Text="• Each nested grid can have its own row and column definitions" Margin="10,0,0,3"/>
    <TextBlock Text="• Logical grouping of UI elements" Margin="10,0,0,3"/>
    <TextBlock Text="• Better organization and maintenance of complex layouts" Margin="10,0,0,3"/>
</StackPanel>  
```
[/tab]  
[tab=C#|url=https://github.com/OpenSilver/samples/blob/master/src/OpenSilver.Samples/OSFSample.GridNesting/GridNestingExample.xaml.cs|text=GitHub: GridNestingExample.xaml.cs]  
```
public partial class GridNestingExample : UserControl  
{  
    public GridNestingExample()  
    {  
        this.InitializeComponent();  
    }  
}  
```
[/tab]  
[/tabgroup]

OpenSilver는 Grid 컨트롤 내부에 다른 Grid 컨트롤을 중첩하여 배치할 수 있으며, 이를 통해 복잡한 레이아웃을 논리적으로 구성할 수 있습니다.

## 중첩 그리드 결과 확인
대시보드 스타일의 레이아웃이 중첩 그리드를 통해 구현되며, 각 영역은 자체적인 행과 열 구조를 가진 그리드로 구성됩니다. 이를 통해 복잡한 UI를 논리적으로 구성하고 관리할 수 있습니다.

[[[DEMO:GRID_NESTING]]]

이 예제는 Grid 중첩을 통한 복잡한 레이아웃 구성 방법과 UI 요소의 논리적 그룹화 기법을 보여줍니다.

# 그리드 정렬 및 여백  
Grid의 자식 요소에 대한 정렬 및 여백 설정 방법을 알아봅니다.

## 정렬 및 여백 소스코드  
아래 예제는 Grid 내에서 자식 요소의 정렬과 여백을 조정하는 방법을 보여줍니다.

[tabgroup]  
[tab=XAML|url=https://github.com/OpenSilver/samples/blob/master/src/OpenSilver.Samples/OSFSample.GridAlignment/GridAlignmentExample.xaml|text=GitHub: GridAlignmentExample.xaml]  
```
<StackPanel HorizontalAlignment="Left">
    <TextBlock Text="Alignment and Margin in Grid" 
               FontWeight="Bold" 
               Margin="0,0,0,10"/>
    
    <Grid Width="500" 
          Height="350" 
          Background="#F0F0F0" 
          ShowGridLines="True">
        <!-- 행 정의 -->
        <Grid.RowDefinitions>
            <RowDefinition Height="*"/>
            <RowDefinition Height="*"/>
            <RowDefinition Height="*"/>
        </Grid.RowDefinitions>
        
        <!-- 열 정의 -->
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="*"/>
            <ColumnDefinition Width="*"/>
            <ColumnDefinition Width="*"/>
        </Grid.ColumnDefinitions>
        
        <!-- 기본 요소 (셀 전체 영역 채움) -->
        <Border Grid.Row="0" Grid.Column="0" Background="#E1F5FE">
            <TextBlock Text="Default (Fills Cell)" 
                       HorizontalAlignment="Center" 
                       VerticalAlignment="Center"/>
        </Border>
        
        <!-- 왼쪽 정렬 -->
        <Border Grid.Row="0" Grid.Column="1" Background="#E1F5FE" Width="120" Height="60" HorizontalAlignment="Left">
            <TextBlock Text="HorizontalAlignment=Left" 
                       TextWrapping="Wrap"
                       HorizontalAlignment="Center" 
                       VerticalAlignment="Center"/>
        </Border>
        
        <!-- 오른쪽 정렬 -->
        <Border Grid.Row="0" Grid.Column="2" Background="#E1F5FE" Width="120" Height="60" HorizontalAlignment="Right">
            <TextBlock Text="HorizontalAlignment=Right" 
                       TextWrapping="Wrap"
                       HorizontalAlignment="Center" 
                       VerticalAlignment="Center"/>
        </Border>
        
        <!-- 상단 정렬 -->
        <Border Grid.Row="1" Grid.Column="0" Background="#E1F5FE" Width="120" Height="60" VerticalAlignment="Top">
            <TextBlock Text="VerticalAlignment=Top" 
                       TextWrapping="Wrap"
                       HorizontalAlignment="Center" 
                       VerticalAlignment="Center"/>
        </Border>
        
        <!-- 중앙 정렬 -->
        <Border Grid.Row="1" Grid.Column="1" Background="#E1F5FE" Width="120" Height="60" 
                HorizontalAlignment="Center" VerticalAlignment="Center">
            <TextBlock Text="Center Aligned (Both)" 
                       TextWrapping="Wrap"
                       HorizontalAlignment="Center" 
                       VerticalAlignment="Center"/>
        </Border>
        
        <!-- 하단 정렬 -->
        <Border Grid.Row="1" Grid.Column="2" Background="#E1F5FE" Width="120" Height="60" VerticalAlignment="Bottom">
            <TextBlock Text="VerticalAlignment=Bottom" 
                       TextWrapping="Wrap"
                       HorizontalAlignment="Center" 
                       VerticalAlignment="Center"/>
        </Border>
        
        <!-- 여백 적용 (왼쪽) -->
        <Border Grid.Row="2" Grid.Column="0" Background="#E1F5FE" Width="120" Height="60" Margin="20,0,0,0">
            <TextBlock Text="Margin=20,0,0,0 (Left)" 
                       TextWrapping="Wrap"
                       HorizontalAlignment="Center" 
                       VerticalAlignment="Center"/>
        </Border>
        
        <!-- 여백 적용 (모든 방향) -->
        <Border Grid.Row="2" Grid.Column="1" Background="#E1F5FE" Width="120" Height="60" Margin="10">
            <TextBlock Text="Margin=10 (All Sides)" 
                       TextWrapping="Wrap"
                       HorizontalAlignment="Center" 
                       VerticalAlignment="Center"/>
        </Border>
        
        <!-- 여백 및 정렬 조합 -->
        <Border Grid.Row="2" Grid.Column="2" Background="#E1F5FE" Width="120" Height="60" 
                HorizontalAlignment="Right" VerticalAlignment="Top" Margin="0,15,15,0">
            <TextBlock Text="Top-Right with Margin" 
                       TextWrapping="Wrap"
                       HorizontalAlignment="Center" 
                       VerticalAlignment="Center"/>
        </Border>
    </Grid>
    
    <TextBlock Text="Alignment Properties:" 
               FontWeight="Bold" 
               Margin="0,20,0,5"/>
               
    <TextBlock Text="• HorizontalAlignment: Left, Center, Right, Stretch (default)" Margin="10,0,0,3"/>
    <TextBlock Text="• VerticalAlignment: Top, Center, Bottom, Stretch (default)" Margin="10,0,0,3"/>
    <TextBlock Text="• Margin: Controls spacing around elements (format: left,top,right,bottom)" Margin="10,0,0,3"/>
</StackPanel>  
```
[/tab]  
[tab=C#|url=https://github.com/OpenSilver/samples/blob/master/src/OpenSilver.Samples/OSFSample.GridAlignment/GridAlignmentExample.xaml.cs|text=GitHub: GridAlignmentExample.xaml.cs]  
```
public partial class GridAlignmentExample : UserControl  
{  
    public GridAlignmentExample()  
    {  
        this.InitializeComponent();  
    }  
}  
```
[/tab]  
[/tabgroup]

OpenSilver는 Grid 컨트롤 내의 자식 요소에 대해 HorizontalAlignment, VerticalAlignment 속성을 통한 정렬과 Margin 속성을 통한 여백 설정을 지원합니다.

## 정렬 및 여백 결과 확인
다양한 정렬 방식과 여백 설정이 적용된 그리드가 표시되며, 각 셀은 서로 다른 정렬 및 여백 설정을 보여줍니다. 기본적으로 요소는 셀 전체를 채우지만, 정렬 속성을 통해 위치를 조정하고 여백을 설정하여 간격을 조절할 수 있습니다.

[[[DEMO:GRID_ALIGNMENT]]]

이 예제는 Grid 내에서 자식 요소의 정렬과 여백을 조정하는 다양한 방법을 보여줍니다.

# 동적 그리드 생성  
코드를 통해 Grid와 그 자식 요소를 동적으로 생성하는 방법을 알아봅니다.

## 동적 생성 소스코드  
아래 예제는 코드 비하인드에서 Grid와 셀을 동적으로 생성하는 방법을 보여줍니다.

[tabgroup]  
[tab=XAML|url=https://github.com/OpenSilver/samples/blob/master/src/OpenSilver.Samples/OSFSample.GridDynamic/GridDynamicExample.xaml|text=GitHub: GridDynamicExample.xaml]  
```
<StackPanel HorizontalAlignment="Left">
    <TextBlock Text="Dynamic Grid Creation" 
               FontWeight="Bold" 
               Margin="0,0,0,10"/>
    
    <StackPanel Orientation="Horizontal" Margin="0,0,0,10">
        <TextBlock Text="Rows:" VerticalAlignment="Center" Margin="0,0,5,0"/>
        <TextBox x:Name="RowsTextBox" Text="3" Width="50" Margin="0,0,15,0"/>
        
        <TextBlock Text="Columns:" VerticalAlignment="Center" Margin="0,0,5,0"/>
        <TextBox x:Name="ColumnsTextBox" Text="3" Width="50" Margin="0,0,15,0"/>
        
        <Button Content="Generate Grid" Click="GenerateGrid_Click" Width="100"/>
    </StackPanel>
    
    <Border x:Name="GridContainer" 
            Width="450" 
            Height="300" 
            Background="#F5F5F5" 
            BorderBrush="#BDBDBD" 
            BorderThickness="1">
        <!-- 동적으로 생성된 그리드가 여기에 추가됩니다 -->
    </Border>
    
    <TextBlock Text="Properties:" 
               FontWeight="Bold" 
               Margin="0,20,0,5"/>
               
    <TextBlock Text="• Enter number of rows and columns" Margin="10,0,0,3"/>
    <TextBlock Text="• Click 'Generate Grid' to create a new grid" Margin="10,0,0,3"/>
    <TextBlock Text="• Grid will be generated with specified dimensions" Margin="10,0,0,3"/>
    <TextBlock Text="• Each cell shows its position (Row, Column)" Margin="10,0,0,3"/>
</StackPanel>  
```
[/tab]  
[tab=C#|url=https://github.com/OpenSilver/samples/blob/master/src/OpenSilver.Samples/OSFSample.GridDynamic/GridDynamicExample.xaml.cs|text=GitHub: GridDynamicExample.xaml.cs]  
```
public partial class GridDynamicExample : UserControl  
{  
    public GridDynamicExample()  
    {  
        this.InitializeComponent();  
    }  

    private void GenerateGrid_Click(object sender, RoutedEventArgs e)  
    {  
        // 입력값 파싱
        if (!int.TryParse(RowsTextBox.Text, out int rows) || rows < 1)
        {
            MessageBox.Show("Please enter a valid number of rows (minimum 1).");
            return;
        }
        
        if (!int.TryParse(ColumnsTextBox.Text, out int columns) || columns < 1)
        {
            MessageBox.Show("Please enter a valid number of columns (minimum 1).");
            return;
        }
        
        // 최대 크기 제한 (성능상의 이유로)
        if (rows > 20 || columns > 20)
        {
            MessageBox.Show("Maximum 20 rows and 20 columns are allowed for this demo.");
            rows = Math.Min(rows, 20);
            columns = Math.Min(columns, 20);
        }
        
        // 새 그리드 생성
        Grid dynamicGrid = new Grid
        {
            ShowGridLines = true,
            Background = new SolidColorBrush(Colors.White)
        };
        
        // 행 정의 추가
        for (int i = 0; i < rows; i++)
        {
            dynamicGrid.RowDefinitions.Add(new RowDefinition { Height = new GridLength(1, GridUnitType.Star) });
        }
        
        // 열 정의 추가
        for (int i = 0; i < columns; i++)
        {
            dynamicGrid.ColumnDefinitions.Add(new ColumnDefinition { Width = new GridLength(1, GridUnitType.Star) });
        }
        
        // 각 셀에 콘텐츠 추가
        for (int row = 0; row < rows; row++)
        {
            for (int col = 0; col < columns; col++)
            {
                // 셀 콘텐츠 생성
                Border cellBorder = new Border
                {
                    Margin = new Thickness(2),
                    Background = GetCellColor(row, col)
                };
                
                TextBlock cellText = new TextBlock
                {
                    Text = $"({row}, {col})",
                    HorizontalAlignment = HorizontalAlignment.Center,
                    VerticalAlignment = VerticalAlignment.Center
                };
                
                cellBorder.Child = cellText;
                
                // 그리드 위치 설정
                Grid.SetRow(cellBorder, row);
                Grid.SetColumn(cellBorder, col);
                
                // 그리드에 추가
                dynamicGrid.Children.Add(cellBorder);
            }
        }
        
        // 기존 내용 제거 후 새 그리드 추가
        GridContainer.Child = dynamicGrid;
    }
    
    private SolidColorBrush GetCellColor(int row, int col)
    {
        // 체스보드 패턴을 위한 색상 선택
        if ((row + col) % 2 == 0)
        {
            return new SolidColorBrush(Color.FromArgb(255, 230, 240, 255)); // 밝은 색
        }
        else
        {
            return new SolidColorBrush(Color.FromArgb(255, 200, 220, 240)); // 어두운 색
        }
    }
}  
```
[/tab]  
[/tabgroup]

OpenSilver는 코드에서 Grid 컨트롤과 그 자식 요소를 동적으로 생성하고 구성할 수 있으며, 이를 통해 런타임에 레이아웃을 조정할 수 있습니다.

## 동적 생성 결과 확인
사용자가 입력한 행과 열 수에 따라 그리드가 동적으로 생성되며, 각 셀은 체스보드 패턴으로 색상이 지정되고 해당 위치 인덱스가 표시됩니다. 이는 런타임에 UI를 동적으로 구성하는 방법을 보여줍니다.

[[[DEMO:GRID_DYNAMIC]]]

이 예제는 코드에서 Grid를 동적으로 생성하고 구성하는 방법과 런타임에 레이아웃을 조정하는 기법을 보여줍니다.

# 정리하며  
OpenSilver의 Grid 컨트롤은 기본 사용법, 크기 설정, 셀 병합, 중첩 그리드, 정렬 및 여백, 동적 생성 등 다양한 기능을 제공합니다. WPF와 유사한 구조를 기반으로 하여, XAML에 익숙한 개발자라면 기존 지식을 활용해 효율적이고 유연한 레이아웃을 구현할 수 있습니다.

이 문서에서 다룬 예제들은 OpenSilver의 강력한 레이아웃 기능을 보여주며, 실제 애플리케이션에서 다양한 요구사항을 충족할 수 있는 유연성을 입증합니다. 특히 행과 열의 다양한 크기 설정, 셀 병합을 통한 복잡한 레이아웃, 그리고 중첩 그리드를 통한 계층적 UI 구조화는 현대적인 웹 애플리케이션 개발에 매우 유용합니다.

OpenSilver는 Grid 컨트롤을 통해 Panel 기반의 XAML 설계를 그대로 지원하며, 이를 웹 환경에서도 네이티브 수준으로 구현할 수 있는 플랫폼으로서의 강점을 드러냅니다. 이러한 특성은 데스크톱, MAUI와 같은 크로스플랫폼 XAML 개발 환경에서의 경험을 자연스럽게 연결하며, 다양한 플랫폼에서 일관된 UI 설계를 가능하게 하는 기반을 제공합니다.

