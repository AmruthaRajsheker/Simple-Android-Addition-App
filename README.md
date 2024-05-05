# Android Addition Calculator

## Overview

This Android application provides a simple calculator functionality allowing users to perform addition calculations on their mobile devices. It's built using Java and Android Studio.

## Equipment Required
- **Android Studio**: Minimum version required is Arctic Fox.

## Algorithm

**Step 1:** Open Android Studio and then click on `File` -> `New` -> `New project`.

**Step 2:** Type the Application name as "Android Addition Calculator" and click `Next`.

**Step 3:** Select the Minimum SDK and click `Next`.

**Step 4:** Select the Empty Activity and click `Next`. Finally, click `Finish`.

**Step 5:** Design layout in `activity_main.xml` to include input fields for two numbers, an addition button, and a text view for displaying the result.

**Step 6:** In the `MainActivity.java` file, implement logic to get input from input fields, perform addition, and display the result.

**Step 7:** Save your changes and run the application on either an emulator or a physical Android device.


## Usage

1. Enter the first number.
2. Enter the second number.
3. Tap the "Add" button.
4. The result will be displayed on the screen.


## PROGRAM


#### MainActivity.java

```java
package com.example.additioncalculator;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {

    EditText num1Input, num2Input;
    Button addButton;
    TextView resultText;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        num1Input = findViewById(R.id.num1Input);
        num2Input = findViewById(R.id.num2Input);
        addButton = findViewById(R.id.addButton);
        resultText = findViewById(R.id.resultText);

        addButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // Get the input values
                String num1Str = num1Input.getText().toString();
                String num2Str = num2Input.getText().toString();

                // Check if input values are not empty
                if (!num1Str.isEmpty() && !num2Str.isEmpty()) {
                    // Parse the input values to integers
                    int num1 = Integer.parseInt(num1Str);
                    int num2 = Integer.parseInt(num2Str);

                    // Calculate the sum
                    int sum = num1 + num2;

                    // Display the result
                    resultText.setText("Result: " + sum);
                } else {
                    // If input values are empty, display an error message
                    resultText.setText("Please enter both numbers!");
                }
            }
        });
    }
}
```

#### activity_main.xml

```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <EditText
        android:id="@+id/num1Input"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter first number"
        android:inputType="number" />

    <EditText
        android:id="@+id/num2Input"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/num1Input"
        android:hint="Enter second number"
        android:inputType="number" />

    <Button
        android:id="@+id/addButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@id/num2Input"
        android:layout_centerHorizontal="true"
        android:text="Add" />

    <TextView
        android:id="@+id/resultText"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@id/addButton"
        android:layout_centerHorizontal="true"
        android:layout_marginTop="20dp"
        android:textSize="20sp" />

</RelativeLayout>
```

## OUTPUT 
<img src="https://github.com/AmruthaRajsheker/Simple-Android-Addition-App/assets/119475943/709bdb67-5257-4979-a00a-207682e5366d" alt="description" style="width: 30%; height: auto;">

## RESULT 

The result of running this Android application will be a simple addition calculator:

- Users can input two numbers into the provided EditText fields.
- Upon clicking the "Add" button, the application will calculate the sum of the two numbers.
- If both input fields are filled, the sum will be displayed below the button.
- If either or both of the input fields are empty, an error message prompting the user to enter both numbers will be displayed instead.

This application provides a basic functionality for performing addition calculations on an Android device.
