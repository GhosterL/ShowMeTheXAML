# ShowMeTheXAML
A WPF component making it easy to show the corresponding XAML for WPF custom styles and controls

[![NuGet Status](http://img.shields.io/nuget/v/ShowMeTheXAML.svg?style=flat&label=ShowMeTheXAML)](https://www.nuget.org/packages/ShowMeTheXAML/)
[![NuGet Status](http://img.shields.io/nuget/v/ShowMeTheXAML.MSBuild.svg?style=flat&label=ShowMeTheXAML.MSBuild)](https://www.nuget.org/packages/ShowMeTheXAML.MSBuild/)
[![NuGet Status](http://img.shields.io/nuget/v/ShowMeTheXAML.AvalonEdit.svg?style=flat&label=ShowMeTheXAML.AvalonEdit)](https://www.nuget.org/packages/ShowMeTheXAML.AvalonEdit/)

[![AppVeyor](https://img.shields.io/appveyor/ci/Keboo/showmethexaml.svg)](https://ci.appveyor.com/project/Keboo/showmethexaml)

## Setup
1. Install the MSBuild package. `PM> Install-Package ShowMeTheXAML.MSBuild` This will also install the `ShowMeTheXAML` package as well.
2. Add the following code in your `App.xaml.cs`
```C#
protected override void OnStartup(StartupEventArgs e)
{
    XamlDisplay.Init();
    base.OnStartup(e);
}
```
3. (Optional) The default template is pretty basic. For a better looking style add the ShowMeTheXAML.AvalonEdit package. `PM> Install-Package ShowMeTheXAML.AvalonEdit`
In App.xaml include the resource dictionary.
```XAML
<Application.Resources>
    <ResourceDictionary>
        <ResourceDictionary.MergedDictionaries>
            <ResourceDictionary Source="pack://application:,,,/ShowMeTheXAML.AvalonEdit;component/Themes/xamldisplayer.xaml" />
        </ResourceDictionary.MergedDictionaries>
    </ResourceDictionary>
</Application.Resources>
```

## Usage
```XAML
<smtx:XamlDisplay Key="SomeUniqueString">
  <StackPanel>
    <Button Content="Some Content" />
    <TextBlock Text="Text" />
  </StackPanel>
</smtx:XamlDisplay>
```

