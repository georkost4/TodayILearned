# The way of Styling in Android

The right way of styling your view's in Android is **NOT** hardcoding but separating your resources .

For example u should not style in this way

```xml
<TextView
    android:id="@+id/heading"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:padding="10dp"
    android:textColor="#000022"
 />
 ```
 
 
Instead you should create each resource be it color , dimension and create **different file** for each resource . Then
you should create a style and reference them inside there . This is a good way of but to improve on that you should
be careful of the variable naming. 

Usage in xml

```xml
<TextView
    android:id="@+id/heading"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"       
    android:textSize="@dimen/text_size_h1"
    android:padding="@dimen/text_content_padding"
    android:textColor="@color/content_text"
 />
 ```
Usage in styles

```xml
<style name="heading_text_style">
    <item name="android:textColor">@color/content_text</item>
    <item name="android:textSize">@dimen/text_size_h2</item>
    <item name="android:layout_margin">@dimen/text_content_margin</item>
    <item name="android:layout_width">match_parent</item>
    <item name="android:layout_height">wrap_content</item>
</style>
```

With
```xml
<TextView
    android:id="@+id/heading"
    android:style="@style/heading_text_style"
/>
```

Styling your user interface means assigning color codes and dimensions to various properties. Like text color, size of icon, text size, background of screen etc etc.

Style is a reusable form of collection of resources. By the way, A theme is also a collection of resources which modifies look and feel of your product. *The minor difference is you apply theme on a bigger level, say a screen(Activity) and you usually apply style on a granular level, say a view*. The difference is so subtle that there is no theme resource in Android. There is only style resource. You apply theme with style tag.

```xml
android:theme="@style/ThemeGrey"
```

Lastly some info of creating your custom attributes for a Style can be found in [this](https://medium.com/mindorks/mastering-android-themes-chapter-4-591e03320182) article.

Example:

attr.xml

```
<attr name="themeColorPrimary" format="reference"/>
Usage
```

```<FrameLayout
    width, height ... other properties
    android:background="?themeColorPrimary">
</FrameLayout>
```
