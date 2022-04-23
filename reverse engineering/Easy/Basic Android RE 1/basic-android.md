# Basic Android RE 1
## Description

![image](https://user-images.githubusercontent.com/84562630/164865951-0e33f917-a208-4115-986b-d97847a7b6d0.png)
## Solution
After downloading this file. I use an online tool to extract this file. http://www.javadecompilers.com/
I started to look for MainActivity.java file. I got it at location:sources/com/example/secondapp/MainActivity.java
```java
package com.example.secondapp;

import android.os.Bundle;
import android.view.View;
import android.widget.EditText;
import android.widget.TextView;
import androidx.appcompat.app.AppCompatActivity;
import org.apache.commons.codec.digest.DigestUtils;

public class MainActivity extends AppCompatActivity {
    /* access modifiers changed from: protected */
    public void onCreate(Bundle bundle) {
        super.onCreate(bundle);
        setContentView((int) C0272R.layout.activity_main);
    }

    public void submitPassword(View view) {
        EditText editText = (EditText) findViewById(C0272R.C0274id.editText2);
        if (DigestUtils.md5Hex(editText.getText().toString()).equalsIgnoreCase("b74dec4f39d35b6a2e6c48e637c8aedb")) {
            ((TextView) findViewById(C0272R.C0274id.textView)).setText("Success! CTFlearn{" + editText.getText().toString() + "_is_not_secure!}");
        }
    }
}
```
I use an online md5 decoder to decode this "b74dec4f39d35b6a2e6c48e637c8aedb". https://www.md5online.org

![image](https://user-images.githubusercontent.com/84562630/164866710-eaa00eae-b533-4692-9676-8383907ad0dc.png)

Then i will add above decoder to the "CTFlearn{" + editText.getText().toString() + "_is_not_secure!}");"
## Flag 
CTFlearn{Spring2019_is_not_secure!}

