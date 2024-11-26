
MainActivity.java
 Package com.example.exp2;

import androidx.appcompat.app.AppCompatActivity;
import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;
public class MainActivity extends AppCompatActivity {

    TextView welcome;
    Button phone, sms, website;
    Intent i = new Intent();

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        phone = (Button)findViewById(R.id.b1);
        sms = (Button) findViewById(R.id.b2);
        website = (Button) findViewById(R.id.b3);
        phone.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                i.setAction(Intent.ACTION_DIAL);
                i.setData(Uri.parse("tel:9505061025"));
                startActivity(i);
            }
        });
        sms.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                i.setAction(Intent.ACTION_VIEW);
                i.setData(Uri.parse("sms:9505061025"));
                startActivity(i);
            }
        });
        website.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                i.setAction(Intent.ACTION_VIEW);
                i.setData(Uri.parse("https://www.cmrithyderabad.edu.in/"));
                startActivity(i);
            }
        });
}}


Activity_main.xml

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:background="#fff"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/tv1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Menu options"
        android:textAlignment="center"
        android:textColor="#572623"
        android:textSize="40sp"
        android:textStyle="italic” />

    <Button
        android:id="@+id/b1"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Phone"
        android:textSize="25sp"
        android:textStyle="italic"
        android:textAllCaps="true” />
    <Button
        android:id="@+id/b2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="SMS"
        android:textSize="25sp"
        android:textStyle="italic"
        android:textAllCaps="true"/>
        
    <Button
        android:id="@+id/b3"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
         android:text="Website"
        android:textSize="25sp"
        android:textStyle="italic"
        android:textAllCaps="true"/>
        
</LinearLayout>

            

