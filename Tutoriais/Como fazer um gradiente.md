# Gradiente

drawable -> New resource file -> gradient_background.xml

## `gradient_background.xml`
~~~ java
<?xml version="1.0" encoding="utf-8"?>
<selector xmlns:android="http://schemas.android.com/apk/res/android">
<item>
    <shape>
        <gradient android:angle="90"
            android:startColor="@color/teal_700"
            android:centerColor="@color/button_blue"
            android:endColor="@color/azulao">
        </gradient>
    </shape>
</item>
</selector>
~~~