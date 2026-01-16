# Haso-Sansar
This is my frist repositories 
<br>
Author Dippan sapkota
package com.example.myapp;

import android.os.Bundle;
import androidx.appcompat.app.AppCompatActivity;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        TextView tv = new TextView(this);
        tv.setText("Hello My App!");
        tv.setTextSize(24);

        setContentView(tv);
    }
}