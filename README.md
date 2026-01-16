package com.example.memeapp;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    EditText memeText;
    TextView postView, likeCount, coinCount;
    Button addPost, likeBtn;

    int likes = 0;
    int coins = 0;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        memeText = findViewById(R.id.memeText);
        postView = findViewById(R.id.postView);
        likeCount = findViewById(R.id.likeCount);
        coinCount = findViewById(R.id.coinCount);
        addPost = findViewById(R.id.addPost);
        likeBtn = findViewById(R.id.likeBtn);

        addPost.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String meme = memeText.getText().toString();
                postView.setText(meme);
                memeText.setText("");
                likes = 0;
                coins = 0;
                updateUI();
            }
        });

        likeBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                likes++;
                coins = likes * 2; // 1 like = 2 coins
                updateUI();
            }
        });
    }

    void updateUI() {
        likeCount.setText("Likes: " + likes);
        coinCount.setText("Coins: " + coins);
    }
}