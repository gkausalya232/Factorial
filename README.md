# Ex.No:4 To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## AIM:

To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:
Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as smsintent and click Next.

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Send SMS and Display details give in MainActivity file.

Step 7: Save and run the application.


## PROGRAM:
```
/*
Program to print the text “ExplicitIntent”.
Developed by:Kausalya G
Registeration Number :212221040076
*/
```
## activity_main.xml:

```
activity_main.xml:
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
xmlns:android="http://schemas.android.com/apk/res/android"
     xmlns:app="http://schemas.android.com/apk/res-auto"
      xmlns:tools="http://schemas.android.com/tools"
      android:layout_width="match_parent"
      android:layout_height="match_parent"
      tools:context=".MainActivity">
 <EditText
          android:id="@+id/numberEditText1"
          android:layout_width="wrap_content"
          android:layout_height="wrap_content"
          android:layout_marginTop="172dp"
          android:ems="10"
          android:inputType="textPersonName"
          android:text=""
          app:layout_constraintEnd_toEndOf="parent"
          app:layout_constraintHorizontal_bias="0.497"
          app:layout_constraintStart_toStartOf="parent"
          app:layout_constraintStart_toStartOf="parent"
         app:layout_constraintTop_toTopOf="parent" />
 <Button
         android:id="@+id/factorialButton"
         android:layout_width="wrap_content"
         android:layout_height="wrap_content"
         android:layout_marginTop="340dp"
         android:text="Button"
         app:layout_constraintEnd_toEndOf="parent"
         app:layout_constraintHorizontal_bias="0.498"
         app:layout_constraintStart_toStartOf="parent"
         app:layout_constraintTop_toTopOf="parent" />
</androidx.constraintlayout.widget.ConstraintLayout>
 
```
## activity_main2.xml:
```
activity_main2.xml:
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
xmlns:android="http://schemas.android.com/apk/res/android"
         xmlns:app="http://schemas.android.com/apk/res-auto"
         xmlns:tools="http://schemas.android.com/tools"
         android:layout_width="match_parent"
         android:layout_height="match_parent"
         tools:context=".MainActivity">
 <EditText
                 android:id="@+id/numberEditText1"
         android:layout_width="wrap_content"
         android:layout_height="wrap_content"
         android:layout_marginTop="172dp"
         android:ems="10"
         android:inputType="textPersonName"
         android:text=""
         app:layout_constraintEnd_toEndOf="parent"
         app:layout_constraintHorizontal_bias="0.497"
         app:layout_constraintStart_toStartOf="parent"
         app:layout_constraintTop_toTopOf="parent" />
 <Button
         android:id="@+id/factorialButton"
         android:layout_width="wrap_content"
         android:layout_height="wrap_content"
         android:layout_marginTop="340dp"
         android:text="Button"
         app:layout_constraintEnd_toEndOf="parent"
         app:layout_constraintHorizontal_bias="0.498"
         app:layout_constraintStart_toStartOf="parent"
         app:layout_constraintTop_toTopOf="parent" />
</androidx.constraintlayout.widget.ConstraintLayout>
```
## MainActivity.java:

```
 MainActivity.java:
package com.example.factorialexplicit;
import static com.example.factorialexplicit.R.id.factorialButton;
import static com.example.factorialexplicit.R.id.numberEditText1;
import androidx.appcompat.app.AppCompatActivity;
import android.annotation.SuppressLint;
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
public class MainActivity extends AppCompatActivity {
 private EditText numberEditText;
 private Button factorialButton;
 @Override
       protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        numberEditText = findViewById(R.id.numberEditText1);
               factorialButton = findViewById(R.id.factorialButton);
        factorialButton.setOnClickListener(new View.OnClickListener() {
 @Override
        public void onClick(View v) {
        int number =
       Integer.parseInt(numberEditText.getText().toString());
               Intent intent = new Intent(MainActivity.this,
MainActivity2.class);
 intent.putExtra("number", number);
 startActivity(intent);
        }
     });
   }
}
```
## PROGRAM:
```
package com.example.factorialexplicit;
import static com.example.factorialexplicit.R.id.factorialTextView;
import androidx.appcompat.app.AppCompatActivity;
import android.annotation.SuppressLint;
import android.content.Intent;
import android.os.Bundle;
import android.widget.TextView;
public class MainActivity2 extends AppCompatActivity 
private TextView factorialTextView;
 @SuppressLint("MissingInflatedId")
 @Override
 protected void onCreate(Bundle savedInstanceState) {
          super.onCreate(savedInstanceState);
         setContentView(R.layout.activity_main);
         factorialTextView = findViewById(R.id.factorialButton);
         Intent intent = getIntent();
                 int number = intent.getIntExtra("number", 0);
         long factorial = calculateFactorial(number);
         factorialTextView.setText("Factorial of " + number + " is " +
factorial);
 }
         private long calculateFactorial(int number) {
         long factorial = 1;
 for (int i = 1; i <= number; i++) {
 factorial *= i;
         }
 return factorial;
      }
}

```
## OUTPUT

![WhatsApp Image 2023-06-11 at 14 14 46](https://github.com/gkausalya232/Factorial/assets/133086820/9d3c325f-8cb6-44d8-965b-197f29bd0aeb)
![WhatsApp Image 2023-06-11 at 14 14 47](https://github.com/gkausalya232/Factorial/assets/133086820/736ee734-604f-467a-a98c-05310740745a)



## RESULT
Thus a Simple Android Application create a Explicit Intents using Android Studio is developed and executed successfully.

