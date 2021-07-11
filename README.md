Androidx Preference 中的padding 硬编码在布局中，无法通过修改属性来完成修改。
当前手机设置中使用的 16dp
 <dimen name="action_bar_content_inset_material">16dp</dimen>

 sw600dp 设备使用的 24dp
 <dimen name="action_bar_content_inset_material">24dp</dimen>
如果要定制只能继承对应的修改对应的样式中的layout ，修改为我们想要的间距要求。

  <!--  设置Preference 主题，继承自 androidx包中的 PreferenceThemeOverlay -->
          <item name="preferenceTheme">@style/PreferenceThemeOverlay</item>

  定义样式，直接基于 androidx 中的样式拿过来，按照我们想要的样式做修改
```xml
      <style name="PreferenceThemeOverlay">

          <!-- switchPreferenceCompat 组件的 样式替换-->
          <item name="switchPreferenceCompatStyle">@style/Preference.SwitchPreferenceCompat.Material</item>
          <!-- switchPreference 组件的 样式替换-->
          <item name="switchPreferenceStyle">@style/Preference.SwitchPreference.Material</item>
          <!-- preference 组件的 样式替换-->
          <item name="preferenceStyle">@style/Preference.Material</item>

      </style>
```

```xml
    <style name="Preference.SwitchPreferenceCompat.Material">
<!--        使用自定义的layout，其中可以使用自定义的 间距-->
        <item name="android:layout">@layout/preference_material_cust</item>
        <item name="allowDividerAbove">false</item>
        <item name="allowDividerBelow">true</item>
        <item name="iconSpaceReserved">@bool/config_materialPreferenceIconSpaceReserved</item>
    </style>
```
```xml
    <style name="Preference.SwitchPreference.Material">
        <!--        使用自定义的layout，其中可以使用自定义的 间距-->
        <item name="android:layout">@layout/preference_material_cust</item>
        <item name="allowDividerAbove">false</item>
        <item name="allowDividerBelow">true</item>
        <item name="iconSpaceReserved">@bool/config_materialPreferenceIconSpaceReserved</item>
    </style>
```
```xml
    <style name="Preference.Material">
        <!--        使用自定义的layout，其中可以使用自定义的 间距-->
        <item name="android:layout">@layout/preference_material_cust</item>
        <item name="allowDividerAbove">false</item>
        <item name="allowDividerBelow">true</item>
        <item name="singleLineTitle">false</item>
        <item name="iconSpaceReserved">@bool/config_materialPreferenceIconSpaceReserved</item>
    </style>
```
