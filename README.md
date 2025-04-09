
# Ex.No:2 Develop an application that uses Font Size using Android Studio.


## AIM:
To develop an application that uses Font Size using android studio.

## EQUIPMENTS REQUIRED:

Android Studio(Min. required Artic Fox)


## ALGORITHM:
Step 1: Create a New Android Project:
              • Click New in the toolbar.
              • In the window that appears, open the Android folder, select Android Application Project,
              and click next.
              • Provide the application name and the project name and then finally give the desired
              package name.
              • Choose a launcher icon for your application and then select Blank Activity and then click
              Next
              • Provide the desired Activity name for your project and then click Finish.

Step 2: Create a New AVD (Android Virtual Device):
        • click Android Virtual Device Manager from the toolbar.
        • In the Android Virtual Device Manager panel, click New.
        • Fill in the details for the AVD. Give it a name, a platform target, an SD card size, and
        a skin (HVGA is default).
        • Click Create AVD and Select the new AVD from the Android Virtual Device
        Manager and click Start.

Step 3: Design the graphical layout with a text view and two command buttons.

Step 4: Run the application.

Step 5:On pressing the change font size button, the size of the font gets altered.       
       
Step 6:Close the Android project. 


## Program:
 ```
/*
Program to Develop an application that uses Font Size using Android Studio .
Developed by: DHANUSH.A
RegisterNumber:  212222220010
*/
```
## MainActivity.java:

```

package com.example.fontcolorchangerapp;

import android.graphics.Color;
import android.graphics.Typeface;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;
import androidx.appcompat.app.AppCompatActivity;
import androidx.core.content.res.ResourcesCompat;

public class MainActivity extends AppCompatActivity {

    TextView sampleText;
    Button changeColorButton, changeFontButton;
    int colorIndex = 0;
    int[] colors = {Color.RED, Color.GREEN, Color.BLUE, Color.MAGENTA};

    boolean isCustomFont = false;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        sampleText = findViewById(R.id.sampleText);
        changeColorButton = findViewById(R.id.changeColorButton);
        changeFontButton = findViewById(R.id.changeFontButton);

        changeColorButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                sampleText.setTextColor(colors[colorIndex]);
                colorIndex = (colorIndex + 1) % colors.length;
            }
        });

        changeFontButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                if (isCustomFont) {
                    sampleText.setTypeface(Typeface.DEFAULT);
                } else {
                    Typeface customTypeface = ResourcesCompat.getFont(MainActivity.this, R.font.oswald);
                    sampleText.setTypeface(customTypeface);
                }
                isCustomFont = !isCustomFont;
            }
        });
    }
}

```



## activity_main.xml:

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:padding="20dp"
    android:background="#FFFFFF">

    <TextView
        android:id="@+id/sampleText"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello Android!"
        android:textSize="24sp"
        android:textColor="#000000"
        android:layout_marginBottom="30dp" />

    <Button
        android:id="@+id/changeColorButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Change Color" />

    <Button
        android:id="@+id/changeFontButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Change Font"
        android:layout_marginTop="20dp" />
</LinearLayout>

```
## Output:


![image](https://github.com/user-attachments/assets/fda448cd-d80e-446f-a643-4f1575d3d378)

![image](https://github.com/user-attachments/assets/08d1174c-70ca-47ef-bfa1-738ab19bd501)



## Result:
Thus, the program for android application, Font Size was executed successfully using Android Studio.
