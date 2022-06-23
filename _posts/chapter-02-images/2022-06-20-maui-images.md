---
title: Handling images in .NET MAUI
author: Siddharth Singh
date: 2022-06-20
category: xaml
layout: post
---

## Images in .NET MAUI
    Importance of images in App.
    How image are represented.
    Where they are used.


## Showing image in the project
```
<Image Source="dotnet_bot.png"/>
```
# Adding a Description for accessiblity

```
<Image 
Source="dotnet_bot.png"
SemanticProperties.Description="Cute dot net bot waving hi to you!"
/>
```

# Fixing the height of the image
```
<Image 
Source="dotnet_bot.png"
HeightRequest="200"
/>
```

# Fixing the Width of the image

```
<Image 
Source="dotnet_bot.png"
WidthRequest="200"
/>
```

## How to load a image from the web in your maui App?

```
<Image
    Source="https://picsum.photos/200"               
    HeightRequest="200"
    HorizontalOptions="Center"
    />
```

## How to add an image to the MAUI project?
You can add a image by simply dragging it to the */Resources/Images* folder in your MAUI project. 

Build action has to be set to MauiImage.
Or you can copy and paste it to Visual studio.
There is splash screen, icon and image types in the build action.


## How to show a rounded image in .NET MAUI?
We need to show clip the bounds.

**Using the Frame,  IsClippedToBounds="True" and Negative Margin**

```
<Frame Margin="10"
       BorderColor="Black"
       CornerRadius="50"
       HeightRequest="60"
       WidthRequest="60"
       IsClippedToBounds="True"
       HorizontalOptions="Center"
       VerticalOptions="Center">
  <Image Source="outdoors.jpg"
         Aspect="AspectFill"
         Margin="-20"
         HeightRequest="100"
         WidthRequest="100" />
</Frame>
```


**Using the Image.Clip**

```
 <Image  HorizontalOptions="Center"
                        VerticalOptions="Center"
                        Grid.Column="1"
                        WidthRequest="75"
                        HeightRequest="75"
                        Aspect="AspectFill"
                        Source="https://devblogs.microsoft.com/xamarin/wp-content/uploads/sites/44/2019/03/Screen-Shot-2017-01-03-at-3.35.53-PM-150x150.png">
                    <Image.Clip>
                        <EllipseGeometry 
                                Center="36,36"
                                RadiusX="36"
                                RadiusY="36"/>
                    </Image.Clip>
                </Image>
 <Image  HorizontalOptions="Center"
                        VerticalOptions="Center"
                        Grid.Column="1"
                        WidthRequest="75"
                        HeightRequest="75"
                        Aspect="AspectFill"
                        Source="https://devblogs.microsoft.com/xamarin/wp-content/uploads/sites/44/2019/03/Screen-Shot-2017-01-03-at-3.35.53-PM-150x150.png">
                    <Image.Clip>
                        <EllipseGeometry 
                                Center="36,36"
                                RadiusX="36"
                                RadiusY="36"/>
                    </Image.Clip>
                </Image>
                
```


# How to display images in a Grid view ?

```
   public class WebImage
    {
        public string Url { get; set; }
    }
```


```
namespace Images;
public partial class MainPage : ContentPage
{
    public List<WebImage> ImageList { get; set; }
    public MainPage()
	{
		InitializeComponent();
		GetData();
        BindingContext = this;
	}

    private void GetData()
    {
        var list = new List<WebImage>();
        for(int i = 0; i < 20; i++)
        {
            list.Add(new WebImage() { Url = "https://picsum.photos/50" });
        }
        ImageList = list;
    }
}

```


```
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             x:Class="Images.MainPage">  
   
    <CollectionView ItemsSource="{Binding ImageList}"
                ItemsLayout="VerticalGrid, 3">
            <CollectionView.ItemTemplate>
                <DataTemplate>              
                        <Image Margin="10"
                       Source="{Binding Url}"
                       Aspect="AspectFill"
                      />                 
            </DataTemplate>
        </CollectionView.ItemTemplate>
    </CollectionView>
</ContentPage>
```



## How to display full screen images?

## How to show a image in a button in .net MAUI?
**Approach 1: Using the Image button **

```
    <ImageButton Source="dotnet_bot.png"
                 Margin="100,100,100,100"
                 BackgroundColor="Beige"
                 WidthRequest="100"
                 HeightRequest="200"
                    HorizontalOptions="Center"
                    VerticalOptions="Center" />
```

**Approach 2: Using the Image source property in the Button **
```
 <Button ImageSource="dotnet_bot.png"                
                 BackgroundColor="Beige"
                 WidthRequest="400"
                 HeightRequest="100"
                    HorizontalOptions="Center"
                    VerticalOptions="Center" />
```



## How to make a image clickable in .NET MAUI?

```
    <Image x:Name="myImage" Source="dotnet_bot.png"                
                 BackgroundColor="Beige"
                 WidthRequest="400"
                 HeightRequest="100"
                    HorizontalOptions="Center"
                    VerticalOptions="Center" >
        <Image.GestureRecognizers>
            <TapGestureRecognizer Tapped="Imageclicked"/>
        </Image.GestureRecognizers>
    </Image>
</ContentPage>

```

```
public partial class MainPage : ContentPage
{
    public MainPage()
	{
		InitializeComponent();	
      
	}

	private async void Imageclicked(object sender, System.EventArgs e)
    {
        this.myImage.BackgroundColor = this.myImage.BackgroundColor == Microsoft.Maui.Graphics.Colors.Magenta ? Microsoft.Maui.Graphics.Colors.Beige : Microsoft.Maui.Graphics.Colors.Magenta;
    }
}

```

## How to load a GIF in your .NET MAUI App?

## How to save an image in .NET MAUI?

## How to apply a filter to image in .NET MAUI?

## How to change image transparency in .NET MAUI ?

## How to load image from a stream ?

## How to load an embedded image?

## How to display iamges with a shadow ?

## How to display image with a border?

## How to overlap an image over another control?

## How to add text over an image ?

## How to make an image grayscale ?

## How to share an image in .NET MAUI?

## How to cache an image?

## How to resize an image?

## How to downsize an image?
