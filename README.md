package com.example.imagebutton;  

import android.annotation.SuppressLint;  
import android.os.Bundle;  
import android.view.View;  
import android.widget.Button;  
import android.widget.ImageView;  
import android.widget.Toast;  

import androidx.activity.EdgeToEdge;  
import androidx.appcompat.app.AppCompatActivity;  
import androidx.core.graphics.Insets;  
import androidx.core.view.ViewCompat;  
import androidx.core.view.WindowInsetsCompat;  

public class MainActivity extends AppCompatActivity {  
    ImageView imageView;  
    Button button;  
    int img=1;  
    @SuppressLint("MissingInflatedId")  
    @Override  
    protected void onCreate(Bundle savedInstanceState) {  
        super.onCreate(savedInstanceState);  
        EdgeToEdge.enable(this);  
        setContentView(R.layout.activity_main);  
        ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main), (v, insets) -> {  
            Insets systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars());  
            v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom);  
            return insets;  
        });  

        imageView = findViewById(R.id.imageView);  
        button = findViewById(R.id.button);  
  
        imageView.setOnClickListener(new View.OnClickListener() {  
            @Override  
            public void onClick(View v) {  
                Toast.makeText(MainActivity.this, "This is cat", Toast.LENGTH_SHORT).show();  
            }  
        });  
  
        button.setOnClickListener(new View.OnClickListener() {  
            @Override  
            public void onClick(View v) {  
                if(img ==1){    
                    imageView.setImageResource(R.drawable.couplegoal);  
                    img=2;  
                }else if (img ==3); {  
                    imageView.setImageResource(R.drawable.visionboard);  
                    img = 3;  
                } else{  
                    imageView.setImageResource(R.drawable.bingo);  
                }  
            }    
        });    
    }  
}  
