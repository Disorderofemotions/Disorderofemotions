<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="fill_parent"
    android:layout_height="fill_parent"
    android:orientation="vertical" >

    <LinearLayout
        android:id="@+id/linearLayout1"
        android:layout_width="fill_parent"
        android:layout_height="wrap_content" >

        <TextView
            android:id="@+id/textView1"
            android:layout_width="60dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:textSize="25dp"
            android:text="Угол XY" />

        <TextView
            android:id="@+id/xyValue"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:textSize="25dp"
            android:text="0" />

    </LinearLayout>

    <LinearLayout
        android:id="@+id/linearLayout2"
        android:layout_width="fill_parent"
        android:layout_height="wrap_content" >

        <TextView
            android:id="@+id/textView3"
            android:layout_width="60dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:textSize="25dp"
            android:text="Угол XZ" /> />

        <TextView
            android:id="@+id/xzValue"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:textSize="25dp"
            android:text="0" />

    </LinearLayout>

    <LinearLayout
        android:id="@+id/linearLayout3"
        android:layout_width="fill_parent"
        android:layout_height="wrap_content" >

        <TextView
            android:id="@+id/textView5"
            android:layout_width="60dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:textSize="25dp"
            android:text="Угол ZY" />

        <TextView
            android:id="@+id/zyValue"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:textSize="25dp"
            android:text="0" />

    </LinearLayout>

</LinearLayout>
