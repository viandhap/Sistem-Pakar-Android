# Sistem-Pakar-Android
Sistem Pakar Android dengan metode certainty factor - Skripsi
=================================================================
Listing Program
=================================================================


AndroidManifest.xml

<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.sistempakarpencernaan">

    <uses-permission android:name="android.permission.CALL_PHONE" />

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.SistemPakarPencernaan">
        <activity android:name=".HighestScoreActivity" />
        <activity android:name=".QuizActivity" />
        <activity android:name=".IsiMenuDispepsia" />
        <activity android:name=".IsiMenuUsusbuntu" />
        <activity android:name=".IsiMenuKonstipasi" />
        <activity android:name=".IsiMenuGerd" />
        <activity android:name=".IsiMenuGastritis" />
        <activity android:name=".IsiMenuTukaklambung" />
        <activity android:name=".IsiMenuGastroenteritis" />
        <activity android:name=".IsiMenuDiare" />
        <activity android:name=".MenuInformasi" />
        <activity android:name=".MenuTips" />
        <activity android:name=".MenuTentang" />
        <activity android:name=".MainActivity" />
        <activity android:name=".MenuAwal" />
        <activity android:name=".MenuSplashscreen">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>

MenuSplashscreen.java

package com.example.sistempakarpencernaan;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.os.Handler;
import android.view.Window;

public class MenuSplashscreen extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        //
        this.requestWindowFeature(Window.FEATURE_NO_TITLE);
        setContentView(R.layout.activity_menu_splashscreen);

        final Handler handler = new Handler();
        handler.postDelayed(new Runnable() {
            @Override
            public void run() {
                startActivity(new Intent(getApplicationContext(), MenuAwal.class));
                finish();
            }
        }, 2000);
    }
}

activity_menu_splashscreen.xml

<?xml version="1.0" encoding="utf-8"?>
<ScrollView
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/bgsplash"
    tools:context=".MenuSplashscreen">

</ScrollView>


MenuAwal.java

package com.example.sistempakarpencernaan;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.provider.ContactsContract;
import android.view.View;
import android.widget.ImageButton;

public class MenuAwal extends AppCompatActivity {
    private ImageButton imgbtn1, imgbtn7, imgbtn4, imgbtn8, imgbtn2,imgbtn6;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_menu_awal);

        imgbtn1 = (ImageButton) findViewById(R.id.imageButton1);
        imgbtn1.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                openMainActivity();
            }
        });

        imgbtn7 = (ImageButton) findViewById(R.id.imageButton7);
        imgbtn7.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                openTentangActivity();
            }
        });

        imgbtn4 = (ImageButton) findViewById(R.id.imageButton4);
        imgbtn4.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                openTipsActivity();
            }
        });

        imgbtn8 = (ImageButton) findViewById(R.id.imageButton8);
        imgbtn8.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                closeActivity();
            }
        });

        imgbtn2 = (ImageButton) findViewById(R.id.imageButton2);
        imgbtn2.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) { openInformasiActivity();}
        });
        imgbtn6 = (ImageButton) findViewById(R.id.imageButton6);
        imgbtn6.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) { openQuizActivity(); }
        });
    }

    public void openMainActivity() {
        Intent intent = new Intent(this, MainActivity.class);
        startActivity(intent);
    }
    public void openTentangActivity(){
        Intent intent1 = new Intent(this, MenuTentang.class);
        startActivity(intent1);
    }
    public void openTipsActivity(){
        Intent intent2 = new Intent(this, MenuTips.class);
        startActivity(intent2);
    }
    public void closeActivity(){
        System.exit(0);
    }

    public void openInformasiActivity(){
        Intent intent3 = new Intent(this, MenuInformasi.class);
        startActivity(intent3);
    }
    public void openQuizActivity(){
        Intent intent6 = new Intent(this, QuizActivity.class);
        startActivity(intent6);
    }
}

acticity_menu_awal.xml

<?xml version="1.0" encoding="utf-8"?>
<ScrollView
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/backgroundbasic3"
    tools:context=".MenuAwal">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical">

        <ImageView
            android:id="@+id/imageView2"
            android:layout_width="wrap_content"
            android:layout_height="102dp"
            android:layout_weight="1"
            app:srcCompat="@drawable/labelawal" />
        <RelativeLayout
            android:layout_width="wrap_content"
            android:layout_height="wrap_content">

            <ImageButton
                android:id="@+id/imageButton1"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_marginLeft="25dp"
                app:srcCompat="@drawable/buttondeteksi2" />

            <ImageButton
                android:id="@+id/imageButton2"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_marginLeft="190dp"
                app:srcCompat="@drawable/buttoninformasi2" />

        </RelativeLayout>

        <RelativeLayout
            android:layout_width="wrap_content"
            android:layout_height="wrap_content">

            <ImageButton
                android:id="@+id/imageButton4"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_marginLeft="25dp"
                app:srcCompat="@drawable/buttontipssehat2" />

            <ImageButton
                android:id="@+id/imageButton6"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_marginLeft="190dp"
                app:srcCompat="@drawable/buttonquiz2" />

        </RelativeLayout>

        <RelativeLayout
            android:layout_width="wrap_content"
            android:layout_height="wrap_content">

            <ImageButton
                android:id="@+id/imageButton7"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_marginLeft="25dp"
                app:srcCompat="@drawable/buttontentang2" />

            <ImageButton
                android:id="@+id/imageButton8"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_marginLeft="190dp"
                app:srcCompat="@drawable/buttonkeluar2" />

        </RelativeLayout>

    </LinearLayout>

</ScrollView>

MainActivity.java

package com.example.sistempakarpencernaan;

import androidx.appcompat.app.AlertDialog;
import androidx.appcompat.app.AppCompatActivity;

import android.content.DialogInterface;
import android.os.Bundle;
import android.view.View;
import android.widget.ArrayAdapter;
import android.widget.AutoCompleteTextView;
import android.widget.CheckBox;
import android.widget.ImageButton;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {

    ImageButton imgbtn;
    TextView tvOutput;
    CheckBox chkGejala1, chkGejala2, chkGejala3, chkGejala4, chkGejala5, chkGejala6, chkGejala7, chkGejala8, chkGejala9, chkGejala10, chkGejala11, chkGejala12, chkGejala13, chkGejala14, chkGejala15, chkGejala16, chkGejala17, chkGejala18, chkGejala19, chkGejala20, chkGejala21, chkGejala22, chkGejala23, chkGejala24, chkGejala25;
    AutoCompleteTextView txtNilaiGejala1, txtNilaiGejala2, txtNilaiGejala3, txtNilaiGejala4, txtNilaiGejala5, txtNilaiGejala6, txtNilaiGejala7, txtNilaiGejala8, txtNilaiGejala9, txtNilaiGejala10, txtNilaiGejala11, txtNilaiGejala12, txtNilaiGejala13, txtNilaiGejala14, txtNilaiGejala15, txtNilaiGejala16, txtNilaiGejala17, txtNilaiGejala18, txtNilaiGejala19, txtNilaiGejala20, txtNilaiGejala21, txtNilaiGejala22, txtNilaiGejala23, txtNilaiGejala24, txtNilaiGejala25;

    String[] nilaiKeyakinanGejala1 = {"0", "0.2", "0.4", "0.6", "0.8", "1"};
    String[] nilaiKeyakinanGejala2 = {"0", "0.2", "0.4", "0.6", "0.8", "1"};
    String[] nilaiKeyakinanGejala3 = {"0", "0.2", "0.4", "0.6", "0.8", "1"};
    String[] nilaiKeyakinanGejala4 = {"0", "0.2", "0.4", "0.6", "0.8", "1"};
    String[] nilaiKeyakinanGejala5 = {"0", "0.2", "0.4", "0.6", "0.8", "1"};
    String[] nilaiKeyakinanGejala6 = {"0", "0.2", "0.4", "0.6", "0.8", "1"};
    String[] nilaiKeyakinanGejala7 = {"0", "0.2", "0.4", "0.6", "0.8", "1"};
    String[] nilaiKeyakinanGejala8 = {"0", "0.2", "0.4", "0.6", "0.8", "1"};
    String[] nilaiKeyakinanGejala9 = {"0", "0.2", "0.4", "0.6", "0.8", "1"};
    String[] nilaiKeyakinanGejala10 = {"0", "0.2", "0.4", "0.6", "0.8", "1"};
    String[] nilaiKeyakinanGejala11 = {"0", "0.2", "0.4", "0.6", "0.8", "1"};
    String[] nilaiKeyakinanGejala12 = {"0", "0.2", "0.4", "0.6", "0.8", "1"};
    String[] nilaiKeyakinanGejala13 = {"0", "0.2", "0.4", "0.6", "0.8", "1"};
    String[] nilaiKeyakinanGejala14 = {"0", "0.2", "0.4", "0.6", "0.8", "1"};
    String[] nilaiKeyakinanGejala15 = {"0", "0.2", "0.4", "0.6", "0.8", "1"};
    String[] nilaiKeyakinanGejala16 = {"0", "0.2", "0.4", "0.6", "0.8", "1"};
    String[] nilaiKeyakinanGejala17 = {"0", "0.2", "0.4", "0.6", "0.8", "1"};
    String[] nilaiKeyakinanGejala18 = {"0", "0.2", "0.4", "0.6", "0.8", "1"};
    String[] nilaiKeyakinanGejala19 = {"0", "0.2", "0.4", "0.6", "0.8", "1"};
    String[] nilaiKeyakinanGejala20 = {"0", "0.2", "0.4", "0.6", "0.8", "1"};
    String[] nilaiKeyakinanGejala21 = {"0", "0.2", "0.4", "0.6", "0.8", "1"};
    String[] nilaiKeyakinanGejala22 = {"0", "0.2", "0.4", "0.6", "0.8", "1"};
    String[] nilaiKeyakinanGejala23 = {"0", "0.2", "0.4", "0.6", "0.8", "1"};
    String[] nilaiKeyakinanGejala24 = {"0", "0.2", "0.4", "0.6", "0.8", "1"};
    String[] nilaiKeyakinanGejala25 = {"0", "0.2", "0.4", "0.6", "0.8", "1"};

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        imgbtn = (ImageButton)findViewById(R.id.imageButton);
        tvOutput = (TextView)findViewById(R.id.textView);
        chkGejala1 = (CheckBox)findViewById(R.id.checkBox);
        chkGejala2 = (CheckBox)findViewById(R.id.checkBox2);
        chkGejala3 = (CheckBox)findViewById(R.id.checkBox3);
        chkGejala4 = (CheckBox)findViewById(R.id.checkBox4);
        chkGejala5 = (CheckBox)findViewById(R.id.checkBox5);
        chkGejala6 = (CheckBox)findViewById(R.id.checkBox6);
        chkGejala7 = (CheckBox)findViewById(R.id.checkBox7);
        chkGejala8 = (CheckBox)findViewById(R.id.checkBox8);
        chkGejala9 = (CheckBox)findViewById(R.id.checkBox9);
        chkGejala10 = (CheckBox)findViewById(R.id.checkBox10);
        chkGejala11 = (CheckBox)findViewById(R.id.checkBox11);
        chkGejala12 = (CheckBox)findViewById(R.id.checkBox12);
        chkGejala13 = (CheckBox)findViewById(R.id.checkBox13);
        chkGejala14 = (CheckBox)findViewById(R.id.checkBox14);
        chkGejala15 = (CheckBox)findViewById(R.id.checkBox15);
        chkGejala16 = (CheckBox)findViewById(R.id.checkBox16);
        chkGejala17 = (CheckBox)findViewById(R.id.checkBox17);
        chkGejala18 = (CheckBox)findViewById(R.id.checkBox18);
        chkGejala19 = (CheckBox)findViewById(R.id.checkBox19);
        chkGejala20 = (CheckBox)findViewById(R.id.checkBox20);
        chkGejala21 = (CheckBox)findViewById(R.id.checkBox21);
        chkGejala22 = (CheckBox)findViewById(R.id.checkBox22);
        chkGejala23 = (CheckBox)findViewById(R.id.checkBox23);
        chkGejala24 = (CheckBox)findViewById(R.id.checkBox24);
        chkGejala25 = (CheckBox)findViewById(R.id.checkBox25);

        txtNilaiGejala1 = (AutoCompleteTextView)findViewById(R.id.autoCompleteTextView);
        txtNilaiGejala2 = (AutoCompleteTextView)findViewById(R.id.autoCompleteTextView2);
        txtNilaiGejala3 = (AutoCompleteTextView)findViewById(R.id.autoCompleteTextView3);
        txtNilaiGejala4 = (AutoCompleteTextView)findViewById(R.id.autoCompleteTextView4);
        txtNilaiGejala5 = (AutoCompleteTextView)findViewById(R.id.autoCompleteTextView5);
        txtNilaiGejala6 = (AutoCompleteTextView)findViewById(R.id.autoCompleteTextView6);
        txtNilaiGejala7 = (AutoCompleteTextView)findViewById(R.id.autoCompleteTextView7);
        txtNilaiGejala8 = (AutoCompleteTextView)findViewById(R.id.autoCompleteTextView8);
        txtNilaiGejala9 = (AutoCompleteTextView)findViewById(R.id.autoCompleteTextView9);
        txtNilaiGejala10 = (AutoCompleteTextView)findViewById(R.id.autoCompleteTextView10);
        txtNilaiGejala11 = (AutoCompleteTextView)findViewById(R.id.autoCompleteTextView11);
        txtNilaiGejala12 = (AutoCompleteTextView)findViewById(R.id.autoCompleteTextView12);
        txtNilaiGejala13 = (AutoCompleteTextView)findViewById(R.id.autoCompleteTextView13);
        txtNilaiGejala14 = (AutoCompleteTextView)findViewById(R.id.autoCompleteTextView14);
        txtNilaiGejala15 = (AutoCompleteTextView)findViewById(R.id.autoCompleteTextView15);
        txtNilaiGejala16 = (AutoCompleteTextView)findViewById(R.id.autoCompleteTextView16);
        txtNilaiGejala17 = (AutoCompleteTextView)findViewById(R.id.autoCompleteTextView17);
        txtNilaiGejala18 = (AutoCompleteTextView)findViewById(R.id.autoCompleteTextView18);
        txtNilaiGejala19 = (AutoCompleteTextView)findViewById(R.id.autoCompleteTextView19);
        txtNilaiGejala20 = (AutoCompleteTextView)findViewById(R.id.autoCompleteTextView20);
        txtNilaiGejala21 = (AutoCompleteTextView)findViewById(R.id.autoCompleteTextView21);
        txtNilaiGejala22 = (AutoCompleteTextView)findViewById(R.id.autoCompleteTextView22);
        txtNilaiGejala23 = (AutoCompleteTextView)findViewById(R.id.autoCompleteTextView23);
        txtNilaiGejala24 = (AutoCompleteTextView)findViewById(R.id.autoCompleteTextView24);
        txtNilaiGejala25 = (AutoCompleteTextView)findViewById(R.id.autoCompleteTextView25);

        final ArrayAdapter<String> adapterGejala1 = new ArrayAdapter<String>
                (this, android.R.layout.select_dialog_item, nilaiKeyakinanGejala1);
        txtNilaiGejala1.setThreshold(1);
        txtNilaiGejala1.setAdapter(adapterGejala1);

        final ArrayAdapter<String> adapterGejala2 = new ArrayAdapter<String>
                (this, android.R.layout.select_dialog_item, nilaiKeyakinanGejala2);
        txtNilaiGejala2.setThreshold(1);
        txtNilaiGejala2.setAdapter(adapterGejala2);

        final ArrayAdapter<String> adapterGejala3 = new ArrayAdapter<String>
                (this, android.R.layout.select_dialog_item, nilaiKeyakinanGejala3);
        txtNilaiGejala3.setThreshold(1);
        txtNilaiGejala3.setAdapter(adapterGejala3);

        final ArrayAdapter<String> adapterGejala4 = new ArrayAdapter<String>
                (this, android.R.layout.select_dialog_item, nilaiKeyakinanGejala4);
        txtNilaiGejala4.setThreshold(1);
        txtNilaiGejala4.setAdapter(adapterGejala4);

        final ArrayAdapter<String> adapterGejala5 = new ArrayAdapter<String>
                (this, android.R.layout.select_dialog_item, nilaiKeyakinanGejala5);
        txtNilaiGejala5.setThreshold(1);
        txtNilaiGejala5.setAdapter(adapterGejala5);

        final ArrayAdapter<String> adapterGejala6 = new ArrayAdapter<String>
                (this, android.R.layout.select_dialog_item, nilaiKeyakinanGejala6);
        txtNilaiGejala6.setThreshold(1);
        txtNilaiGejala6.setAdapter(adapterGejala6);

        final ArrayAdapter<String> adapterGejala7 = new ArrayAdapter<String>
                (this, android.R.layout.select_dialog_item, nilaiKeyakinanGejala7);
        txtNilaiGejala7.setThreshold(1);
        txtNilaiGejala7.setAdapter(adapterGejala7);

        final ArrayAdapter<String> adapterGejala8 = new ArrayAdapter<String>
                (this, android.R.layout.select_dialog_item, nilaiKeyakinanGejala8);
        txtNilaiGejala8.setThreshold(1);
        txtNilaiGejala8.setAdapter(adapterGejala8);

        final ArrayAdapter<String> adapterGejala9 = new ArrayAdapter<String>
                (this, android.R.layout.select_dialog_item, nilaiKeyakinanGejala9);
        txtNilaiGejala9.setThreshold(1);
        txtNilaiGejala9.setAdapter(adapterGejala9);

        final ArrayAdapter<String> adapterGejala10 = new ArrayAdapter<String>
                (this, android.R.layout.select_dialog_item, nilaiKeyakinanGejala10);
        txtNilaiGejala10.setThreshold(1);
        txtNilaiGejala10.setAdapter(adapterGejala10);

        final ArrayAdapter<String> adapterGejala11 = new ArrayAdapter<String>
                (this, android.R.layout.select_dialog_item, nilaiKeyakinanGejala11);
        txtNilaiGejala11.setThreshold(1);
        txtNilaiGejala11.setAdapter(adapterGejala11);

        final ArrayAdapter<String> adapterGejala12 = new ArrayAdapter<String>
                (this, android.R.layout.select_dialog_item, nilaiKeyakinanGejala12);
        txtNilaiGejala12.setThreshold(1);
        txtNilaiGejala12.setAdapter(adapterGejala12);

        final ArrayAdapter<String> adapterGejala13 = new ArrayAdapter<String>
                (this, android.R.layout.select_dialog_item, nilaiKeyakinanGejala13);
        txtNilaiGejala13.setThreshold(1);
        txtNilaiGejala13.setAdapter(adapterGejala13);

        final ArrayAdapter<String> adapterGejala14 = new ArrayAdapter<String>
                (this, android.R.layout.select_dialog_item, nilaiKeyakinanGejala14);
        txtNilaiGejala14.setThreshold(1);
        txtNilaiGejala14.setAdapter(adapterGejala14);

        final ArrayAdapter<String> adapterGejala15 = new ArrayAdapter<String>
                (this, android.R.layout.select_dialog_item, nilaiKeyakinanGejala15);
        txtNilaiGejala15.setThreshold(1);
        txtNilaiGejala15.setAdapter(adapterGejala15);

        final ArrayAdapter<String> adapterGejala16 = new ArrayAdapter<String>
                (this, android.R.layout.select_dialog_item, nilaiKeyakinanGejala16);
        txtNilaiGejala16.setThreshold(1);
        txtNilaiGejala16.setAdapter(adapterGejala16);

        final ArrayAdapter<String> adapterGejala17 = new ArrayAdapter<String>
                (this, android.R.layout.select_dialog_item, nilaiKeyakinanGejala17);
        txtNilaiGejala17.setThreshold(1);
        txtNilaiGejala17.setAdapter(adapterGejala17);

        final ArrayAdapter<String> adapterGejala18 = new ArrayAdapter<String>
                (this, android.R.layout.select_dialog_item, nilaiKeyakinanGejala18);
        txtNilaiGejala18.setThreshold(1);
        txtNilaiGejala18.setAdapter(adapterGejala18);

        final ArrayAdapter<String> adapterGejala19 = new ArrayAdapter<String>
                (this, android.R.layout.select_dialog_item, nilaiKeyakinanGejala19);
        txtNilaiGejala19.setThreshold(1);
        txtNilaiGejala19.setAdapter(adapterGejala19);

        final ArrayAdapter<String> adapterGejala20 = new ArrayAdapter<String>
                (this, android.R.layout.select_dialog_item, nilaiKeyakinanGejala20);
        txtNilaiGejala20.setThreshold(1);
        txtNilaiGejala20.setAdapter(adapterGejala20);

        final ArrayAdapter<String> adapterGejala21 = new ArrayAdapter<String>
                (this, android.R.layout.select_dialog_item, nilaiKeyakinanGejala21);
        txtNilaiGejala21.setThreshold(1);
        txtNilaiGejala21.setAdapter(adapterGejala21);

        final ArrayAdapter<String> adapterGejala22 = new ArrayAdapter<String>
                (this, android.R.layout.select_dialog_item, nilaiKeyakinanGejala22);
        txtNilaiGejala22.setThreshold(1);
        txtNilaiGejala22.setAdapter(adapterGejala22);

        final ArrayAdapter<String> adapterGejala23 = new ArrayAdapter<String>
                (this, android.R.layout.select_dialog_item, nilaiKeyakinanGejala23);
        txtNilaiGejala23.setThreshold(1);
        txtNilaiGejala23.setAdapter(adapterGejala23);

        final ArrayAdapter<String> adapterGejala24 = new ArrayAdapter<String>
                (this, android.R.layout.select_dialog_item, nilaiKeyakinanGejala24);
        txtNilaiGejala24.setThreshold(1);
        txtNilaiGejala24.setAdapter(adapterGejala24);

        final ArrayAdapter<String> adapterGejala25 = new ArrayAdapter<String>
                (this, android.R.layout.select_dialog_item, nilaiKeyakinanGejala25);
        txtNilaiGejala25.setThreshold(1);
        txtNilaiGejala25.setAdapter(adapterGejala25);

        txtNilaiGejala1.setOnClickListener(new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                        new AlertDialog.Builder(MainActivity.this).setTitle("Pilihlah Nilai Gejala 1").
                                setAdapter(adapterGejala1, new DialogInterface.OnClickListener() {
                            @Override
                            public void onClick(DialogInterface dialog, int which) {
                                txtNilaiGejala1.setText(nilaiKeyakinanGejala1[which].toString());
                                dialog.dismiss();
                            }
                        }).create().show();
                    }
                }
        );

        txtNilaiGejala2.setOnClickListener(new View.OnClickListener() {
                   @Override
                   public void onClick(View v) {
                         new AlertDialog.Builder(MainActivity.this).setTitle("Pilihlah Nilai Gejala 2").
                                 setAdapter(adapterGejala2, new DialogInterface.OnClickListener() {
                             @Override
                             public void onClick(DialogInterface dialog, int which) {
                                 txtNilaiGejala2.setText(nilaiKeyakinanGejala2[which].toString());
                                 dialog.dismiss();
                             }
                         }).create().show();
                   }
                }
        );

        txtNilaiGejala3.setOnClickListener(new View.OnClickListener() {
                   @Override
                   public void onClick(View v) {
                         new AlertDialog.Builder(MainActivity.this).setTitle("Pilihlah Nilai Gejala 3").
                                  setAdapter(adapterGejala3, new DialogInterface.OnClickListener() {
                              @Override
                             public void onClick(DialogInterface dialog, int which) {
                                  txtNilaiGejala3.setText(nilaiKeyakinanGejala3[which].toString());
                                  dialog.dismiss();
                               }
                          }).create().show();
                   }
                }
        );

        txtNilaiGejala4.setOnClickListener(new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                           new AlertDialog.Builder(MainActivity.this).setTitle("Pilihlah Nilai Gejala 4").
                                    setAdapter(adapterGejala4, new DialogInterface.OnClickListener() {
                                @Override
                                public void onClick(DialogInterface dialog, int which) {
                                     txtNilaiGejala4.setText(nilaiKeyakinanGejala4[which].toString());
                                     dialog.dismiss();
                                 }
                            }).create().show();
                     }
                   }
        );
        txtNilaiGejala5.setOnClickListener(new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                           new AlertDialog.Builder(MainActivity.this).setTitle("Pilihlah Nilai Gejala 5").
                                    setAdapter(adapterGejala5, new DialogInterface.OnClickListener() {
                               @Override
                               public void onClick(DialogInterface dialog, int which) {
                                    txtNilaiGejala5.setText(nilaiKeyakinanGejala5[which].toString());
                                    dialog.dismiss();
                               }
                            }).create().show();
                     }
                   }
        );

        txtNilaiGejala6.setOnClickListener(new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                           new AlertDialog.Builder(MainActivity.this).setTitle("Pilihlah Nilai Gejala 6").
                                     setAdapter(adapterGejala6, new DialogInterface.OnClickListener() {
                               @Override
                               public void onClick(DialogInterface dialog, int which) {
                                    txtNilaiGejala6.setText(nilaiKeyakinanGejala6[which].toString());
                                    dialog.dismiss();
                               }
                           }).create().show();
                    }
                   }
        );

        txtNilaiGejala7.setOnClickListener(new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                            new AlertDialog.Builder(MainActivity.this).setTitle("Pilihlah Nilai Gejala 7").
                                      setAdapter(adapterGejala7, new DialogInterface.OnClickListener() {
                                @Override
                                public void onClick(DialogInterface dialog, int which) {
                                     txtNilaiGejala7.setText(nilaiKeyakinanGejala7[which].toString());
                                     dialog.dismiss();
                                     }
                            }).create().show();
                    }
                   }
        );

        txtNilaiGejala8.setOnClickListener(new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                           new AlertDialog.Builder(MainActivity.this).setTitle("Pilihlah Nilai Gejala 8").
                                    setAdapter(adapterGejala8, new DialogInterface.OnClickListener() {
                               @Override
                               public void onClick(DialogInterface dialog, int which) {
                                    txtNilaiGejala8.setText(nilaiKeyakinanGejala8[which].toString());
                                    dialog.dismiss();
                               }
                           }).create().show();
                    }
                   }
        );

        txtNilaiGejala9.setOnClickListener(new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                           new AlertDialog.Builder(MainActivity.this).setTitle("Pilihlah Nilai Gejala 9").
                                     setAdapter(adapterGejala9, new DialogInterface.OnClickListener() {
                               @Override
                               public void onClick(DialogInterface dialog, int which) {
                                    txtNilaiGejala9.setText(nilaiKeyakinanGejala9[which].toString());
                                    dialog.dismiss();
                               }
                           }).create().show();
                    }
                   }
        );

        txtNilaiGejala10.setOnClickListener(new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                           new AlertDialog.Builder(MainActivity.this).setTitle("Pilihlah Nilai Gejala 10").
                                    setAdapter(adapterGejala10, new DialogInterface.OnClickListener() {
                               @Override
                               public void onClick(DialogInterface dialog, int which) {
                                    txtNilaiGejala10.setText(nilaiKeyakinanGejala10[which].toString());
                                    dialog.dismiss();
                               }
                           }).create().show();
                    }
                   }
        );

        txtNilaiGejala11.setOnClickListener(new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                           new AlertDialog.Builder(MainActivity.this).setTitle("Pilihlah Nilai Gejala 11").
                                    setAdapter(adapterGejala11, new DialogInterface.OnClickListener() {
                               @Override
                               public void onClick(DialogInterface dialog, int which) {
                                    txtNilaiGejala11.setText(nilaiKeyakinanGejala11[which].toString());
                                    dialog.dismiss();
                               }
                           }).create().show();
                    }
                   }
        );

        txtNilaiGejala12.setOnClickListener(new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                           new AlertDialog.Builder(MainActivity.this).setTitle("Pilihlah Nilai Gejala 12").
                                    setAdapter(adapterGejala12, new DialogInterface.OnClickListener() {
                               @Override
                               public void onClick(DialogInterface dialog, int which) {
                                    txtNilaiGejala12.setText(nilaiKeyakinanGejala12[which].toString());
                                    dialog.dismiss();
                               }
                           }).create().show();
                    }
                  }
        );

        txtNilaiGejala13.setOnClickListener(new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                           new AlertDialog.Builder(MainActivity.this).setTitle("Pilihlah Nilai Gejala 13").
                                    setAdapter(adapterGejala13, new DialogInterface.OnClickListener() {
                               @Override
                               public void onClick(DialogInterface dialog, int which) {
                                    txtNilaiGejala13.setText(nilaiKeyakinanGejala13[which].toString());
                                    dialog.dismiss();
                               }
                           }).create().show();
                    }
                   }
        );

        txtNilaiGejala14.setOnClickListener(new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                           new AlertDialog.Builder(MainActivity.this).setTitle("Pilihlah Nilai Gejala 14").
                                    setAdapter(adapterGejala14, new DialogInterface.OnClickListener() {
                                @Override
                                public void onClick(DialogInterface dialog, int which) {
                                     txtNilaiGejala14.setText(nilaiKeyakinanGejala14[which].toString());
                                     dialog.dismiss();
                                }
                           }).create().show();
                    }
                   }
        );

        txtNilaiGejala15.setOnClickListener(new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                           new AlertDialog.Builder(MainActivity.this).setTitle("Pilihlah Nilai Gejala 15").
                                    setAdapter(adapterGejala15, new DialogInterface.OnClickListener() {
                               @Override
                               public void onClick(DialogInterface dialog, int which) {
                                    txtNilaiGejala15.setText(nilaiKeyakinanGejala15[which].toString());
                                    dialog.dismiss();
                                   }
                              }).create().show();
                    }
                   }
        );

        txtNilaiGejala16.setOnClickListener(new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                           new AlertDialog.Builder(MainActivity.this).setTitle("Pilihlah Nilai Gejala 16").
                                    setAdapter(adapterGejala16, new DialogInterface.OnClickListener() {
                               @Override
                               public void onClick(DialogInterface dialog, int which) {
                                    txtNilaiGejala16.setText(nilaiKeyakinanGejala16[which].toString());
                                    dialog.dismiss();
                                    }
                               }).create().show();
                    }
                   }
        );

        txtNilaiGejala17.setOnClickListener(new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                           new AlertDialog.Builder(MainActivity.this).setTitle("Pilihlah Nilai Gejala 17").
                                    setAdapter(adapterGejala17, new DialogInterface.OnClickListener() {
                               @Override
                               public void onClick(DialogInterface dialog, int which) {
                                    txtNilaiGejala17.setText(nilaiKeyakinanGejala17[which].toString());
                                    dialog.dismiss();
                                    }
                               }).create().show();
                    }
                   }
        );

        txtNilaiGejala18.setOnClickListener(new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                           new AlertDialog.Builder(MainActivity.this).setTitle("Pilihlah Nilai Gejala 18").
                                    setAdapter(adapterGejala18, new DialogInterface.OnClickListener() {
                               @Override
                               public void onClick(DialogInterface dialog, int which) {
                                    txtNilaiGejala18.setText(nilaiKeyakinanGejala18[which].toString());
                                    dialog.dismiss();
                                    }
                              }).create().show();
                    }
                   }
        );

        txtNilaiGejala19.setOnClickListener(new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                           new AlertDialog.Builder(MainActivity.this).setTitle("Pilihlah Nilai Gejala 19").
                                    setAdapter(adapterGejala19, new DialogInterface.OnClickListener() {
                               @Override
                               public void onClick(DialogInterface dialog, int which) {
                                    txtNilaiGejala19.setText(nilaiKeyakinanGejala19[which].toString());
                                    dialog.dismiss();
                                    }
                               }).create().show();
                    }
                   }
        );

        txtNilaiGejala20.setOnClickListener(new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                           new AlertDialog.Builder(MainActivity.this).setTitle("Pilihlah Nilai Gejala 20").
                                    setAdapter(adapterGejala20, new DialogInterface.OnClickListener() {
                               @Override
                               public void onClick(DialogInterface dialog, int which) {
                                    txtNilaiGejala20.setText(nilaiKeyakinanGejala20[which].toString());
                                    dialog.dismiss();
                                   }
                              }).create().show();
                    }
                   }
        );

        txtNilaiGejala21.setOnClickListener(new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                           new AlertDialog.Builder(MainActivity.this).setTitle("Pilihlah Nilai Gejala 21").
                                    setAdapter(adapterGejala21, new DialogInterface.OnClickListener() {
                               @Override
                               public void onClick(DialogInterface dialog, int which) {
                                    txtNilaiGejala21.setText(nilaiKeyakinanGejala21[which].toString());
                                    dialog.dismiss();
                                   }
                              }).create().show();
                   }
                  }
        );

        txtNilaiGejala22.setOnClickListener(new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                           new AlertDialog.Builder(MainActivity.this).setTitle("Pilihlah Nilai Gejala 22").
                                    setAdapter(adapterGejala22, new DialogInterface.OnClickListener() {
                               @Override
                               public void onClick(DialogInterface dialog, int which) {
                                    txtNilaiGejala22.setText(nilaiKeyakinanGejala22[which].toString());
                                    dialog.dismiss();
                                    }
                               }).create().show();
                    }
                   }
        );

        txtNilaiGejala23.setOnClickListener(new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                           new AlertDialog.Builder(MainActivity.this).setTitle("Pilihlah Nilai Gejala 23").
                                    setAdapter(adapterGejala23, new DialogInterface.OnClickListener() {
                               @Override
                               public void onClick(DialogInterface dialog, int which) {
                                    txtNilaiGejala23.setText(nilaiKeyakinanGejala23[which].toString());
                                    dialog.dismiss();
                                    }
                               }).create().show();
                    }
                   }
        );

        txtNilaiGejala24.setOnClickListener(new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                           new AlertDialog.Builder(MainActivity.this).setTitle("Pilihlah Nilai Gejala 24").
                                    setAdapter(adapterGejala24, new DialogInterface.OnClickListener() {
                               @Override
                               public void onClick(DialogInterface dialog, int which) {
                                    txtNilaiGejala24.setText(nilaiKeyakinanGejala24[which].toString());
                                    dialog.dismiss();
                                   }
                               }).create().show();
                    }
                   }
        );

        txtNilaiGejala25.setOnClickListener(new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                           new AlertDialog.Builder(MainActivity.this).setTitle("Pilihlah Nilai Gejala 25").
                                    setAdapter(adapterGejala25, new DialogInterface.OnClickListener() {
                               @Override
                               public void onClick(DialogInterface dialog, int which) {
                                    txtNilaiGejala25.setText(nilaiKeyakinanGejala25[which].toString());
                                    dialog.dismiss();
                                    }
                               }).create().show();
                    }
                   }
        );

        imgbtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                String NamaPenyakit = "Anda Menderita Penyakit :";

                if(chkGejala1.isChecked() && chkGejala2.isChecked() && chkGejala3.isChecked() && chkGejala4.isChecked() && chkGejala5.isChecked()){
                    //nilai dari pakar
                    double nilaiGejala1 = 0.8;
                    double nilaiGejala2 = 0.8;
                    double nilaiGejala3 = 0.2;
                    double nilaiGejala4 = 0.2;
                    double nilaiGejala5 = 0.6;

                    //nilai dari user
                    double doubleGejala1 = Double.parseDouble(txtNilaiGejala1.getText().toString());
                    double doubleGejala2 = Double.parseDouble(txtNilaiGejala2.getText().toString());
                    double doubleGejala3 = Double.parseDouble(txtNilaiGejala3.getText().toString());
                    double doubleGejala4 = Double.parseDouble(txtNilaiGejala4.getText().toString());
                    double doubleGejala5 = Double.parseDouble(txtNilaiGejala5.getText().toString());

                    double hasilHitunganGejala1 = nilaiGejala1 * doubleGejala1;
                    double hasilHitunganGejala2 = nilaiGejala2 * doubleGejala2;
                    double hasilHitunganGejala3 = nilaiGejala3 * doubleGejala3;
                    double hasilHitunganGejala4 = nilaiGejala4 * doubleGejala4;
                    double hasilHitunganGejala5 = nilaiGejala5 * doubleGejala5;

                    double Combine_CF1_CF2 = hasilHitunganGejala1 + hasilHitunganGejala2 * (1 - hasilHitunganGejala1);
                    double Combine_CFold_CF3 = Combine_CF1_CF2 + hasilHitunganGejala3 * (1 - Combine_CF1_CF2);
                    double Combine_CFold_CF4 = Combine_CFold_CF3 + hasilHitunganGejala4 * (1 - Combine_CFold_CF3);
                    double Combine_CFold_CF5 = Combine_CFold_CF4 + hasilHitunganGejala5 * (1 - Combine_CFold_CF4);

                    String hasilHitungGejalaPenyakit1 = String.valueOf((Combine_CFold_CF5 * 100));

                    NamaPenyakit += "\nDiare"+"\n"+hasilHitungGejalaPenyakit1+" %";
                }

                if(chkGejala4.isChecked() && chkGejala6.isChecked() && chkGejala7.isChecked() && chkGejala8.isChecked() && chkGejala9.isChecked() && chkGejala10.isChecked() && chkGejala11.isChecked()){
                    //nilai dari pakar
                    double nilaiGejala4 = 0.8;
                    double nilaiGejala6 = 0.8;
                    double nilaiGejala7 = 0.8;
                    double nilaiGejala8 = 0.8;
                    double nilaiGejala9 = 0.6;
                    double nilaiGejala10 = 0.8;
                    double nilaiGejala11 = 0.8;

                    //nilai dari user
                    double doubleGejala4 = Double.parseDouble(txtNilaiGejala4.getText().toString());
                    double doubleGejala6 = Double.parseDouble(txtNilaiGejala6.getText().toString());
                    double doubleGejala7 = Double.parseDouble(txtNilaiGejala7.getText().toString());
                    double doubleGejala8 = Double.parseDouble(txtNilaiGejala8.getText().toString());
                    double doubleGejala9 = Double.parseDouble(txtNilaiGejala9.getText().toString());
                    double doubleGejala10 = Double.parseDouble(txtNilaiGejala10.getText().toString());
                    double doubleGejala11 = Double.parseDouble(txtNilaiGejala11.getText().toString());

                    double hasilHitunganGejala4 = nilaiGejala4 * doubleGejala4;
                    double hasilHitunganGejala6 = nilaiGejala6 * doubleGejala6;
                    double hasilHitunganGejala7 = nilaiGejala7 * doubleGejala7;
                    double hasilHitunganGejala8 = nilaiGejala8 * doubleGejala8;
                    double hasilHitunganGejala9 = nilaiGejala9 * doubleGejala9;
                    double hasilHitunganGejala10 = nilaiGejala10 * doubleGejala10;
                    double hasilHitunganGejala11 = nilaiGejala11 * doubleGejala11;

                    double Combine_CF4_CF6 = hasilHitunganGejala4 + hasilHitunganGejala6 * (1 - hasilHitunganGejala4);
                    double Combine_CFold_CF7 = Combine_CF4_CF6 + hasilHitunganGejala7 * (1 - Combine_CF4_CF6);
                    double Combine_CFold_CF8 = Combine_CFold_CF7 + hasilHitunganGejala8 * (1 - Combine_CFold_CF7);
                    double Combine_CFold_CF9 = Combine_CFold_CF8 + hasilHitunganGejala9 * (1 - Combine_CFold_CF8);
                    double Combine_CFold_CF10 = Combine_CFold_CF9 + hasilHitunganGejala10 * (1 - Combine_CFold_CF9);
                    double Combine_CFold_CF11 = Combine_CFold_CF10 + hasilHitunganGejala11 * (1 - Combine_CFold_CF10);

                    String hasilHitungGejalaPenyakit2 = String.valueOf((Combine_CFold_CF11 * 100));

                    NamaPenyakit += "\nGastroenteritis"+"\n"+hasilHitungGejalaPenyakit2+" %";
                }

                if(chkGejala4.isChecked() && chkGejala12.isChecked() && chkGejala13.isChecked() && chkGejala6.isChecked() && chkGejala14.isChecked() && chkGejala15.isChecked() && chkGejala16.isChecked() && chkGejala9.isChecked() && chkGejala2.isChecked() && chkGejala10.isChecked()){
                    //nilai dari pakar
                    double nilaiGejala4 = 0.6;
                    double nilaiGejala12 = 0.8;
                    double nilaiGejala13 = 0.8;
                    double nilaiGejala6 = 0.8;
                    double nilaiGejala14 = 0.6;
                    double nilaiGejala15 = 0.6;
                    double nilaiGejala16 = 0.6;
                    double nilaiGejala9 = 0.6;
                    double nilaiGejala2 = 0.8;
                    double nilaiGejala10 = 0.6;

                    //nilai dari user
                    double doubleGejala4 = Double.parseDouble(txtNilaiGejala4.getText().toString());
                    double doubleGejala12 = Double.parseDouble(txtNilaiGejala12.getText().toString());
                    double doubleGejala13 = Double.parseDouble(txtNilaiGejala13.getText().toString());
                    double doubleGejala6 = Double.parseDouble(txtNilaiGejala6.getText().toString());
                    double doubleGejala14 = Double.parseDouble(txtNilaiGejala14.getText().toString());
                    double doubleGejala15 = Double.parseDouble(txtNilaiGejala15.getText().toString());
                    double doubleGejala16 = Double.parseDouble(txtNilaiGejala16.getText().toString());
                    double doubleGejala9 = Double.parseDouble(txtNilaiGejala9.getText().toString());
                    double doubleGejala2 = Double.parseDouble(txtNilaiGejala2.getText().toString());
                    double doubleGejala10 = Double.parseDouble(txtNilaiGejala10.getText().toString());

                    double hasilHitunganGejala4 = nilaiGejala4 * doubleGejala4;
                    double hasilHitunganGejala12 = nilaiGejala12 * doubleGejala12;
                    double hasilHitunganGejala13 = nilaiGejala13 * doubleGejala13;
                    double hasilHitunganGejala6 = nilaiGejala6 * doubleGejala6;
                    double hasilHitunganGejala14 = nilaiGejala14 * doubleGejala14;
                    double hasilHitunganGejala15 = nilaiGejala15 * doubleGejala15;
                    double hasilHitunganGejala16 = nilaiGejala16 * doubleGejala16;
                    double hasilHitunganGejala9 = nilaiGejala9 * doubleGejala9;
                    double hasilHitunganGejala2 = nilaiGejala2 * doubleGejala2;
                    double hasilHitunganGejala10 = nilaiGejala10 * doubleGejala10;

                    double Combine_CF4_CF12 = hasilHitunganGejala4 + hasilHitunganGejala12 * (1 - hasilHitunganGejala4);
                    double Combine_CFold_CF13 = Combine_CF4_CF12 + hasilHitunganGejala13 * (1 - Combine_CF4_CF12);
                    double Combine_CFold_CF6 = Combine_CFold_CF13 + hasilHitunganGejala6 * (1 - Combine_CFold_CF13);
                    double Combine_CFold_CF14 = Combine_CFold_CF6 + hasilHitunganGejala14 * (1 - Combine_CFold_CF6);
                    double Combine_CFold_CF15 = Combine_CFold_CF14 + hasilHitunganGejala15 * (1 - Combine_CFold_CF14);
                    double Combine_CFold_CF16 = Combine_CFold_CF15 + hasilHitunganGejala16 * (1 - Combine_CFold_CF15);
                    double Combine_CFold_CF9_1 = Combine_CFold_CF16 + hasilHitunganGejala9 * (1 - Combine_CFold_CF16);
                    double Combine_CFold_CF2 = Combine_CFold_CF9_1 + hasilHitunganGejala2 * (1 - Combine_CFold_CF9_1);
                    double Combine_CFold_CF10_1 = Combine_CFold_CF2 + hasilHitunganGejala10 * (1 - Combine_CFold_CF2);

                    String hasilHitungGejalaPenyakit3 = String.valueOf((Combine_CFold_CF10_1 * 100));

                    NamaPenyakit += "\nTukak Lambung"+"\n"+hasilHitungGejalaPenyakit3+" %";
                }

                if(chkGejala4.isChecked() && chkGejala13.isChecked() && chkGejala6.isChecked() && chkGejala7.isChecked() && chkGejala9.isChecked() && chkGejala2.isChecked() && chkGejala10.isChecked()){
                    //nilai dari pakar
                    double nilaiGejala4 = 0.8;
                    double nilaiGejala13 = 0.6;
                    double nilaiGejala6 = 0.6;
                    double nilaiGejala7 = 0.6;
                    double nilaiGejala9 = 0.6;
                    double nilaiGejala2 = 0.6;
                    double nilaiGejala10 = 0.6;

                    //nilai dari user
                    double doubleGejala4 = Double.parseDouble(txtNilaiGejala4.getText().toString());
                    double doubleGejala13 = Double.parseDouble(txtNilaiGejala13.getText().toString());
                    double doubleGejala6 = Double.parseDouble(txtNilaiGejala6.getText().toString());
                    double doubleGejala7 = Double.parseDouble(txtNilaiGejala7.getText().toString());
                    double doubleGejala9 = Double.parseDouble(txtNilaiGejala9.getText().toString());
                    double doubleGejala2 = Double.parseDouble(txtNilaiGejala2.getText().toString());
                    double doubleGejala10 = Double.parseDouble(txtNilaiGejala10.getText().toString());

                    double hasilHitunganGejala4 = nilaiGejala4 * doubleGejala4;
                    double hasilHitunganGejala13 = nilaiGejala13 * doubleGejala13;
                    double hasilHitunganGejala6 = nilaiGejala6 * doubleGejala6;
                    double hasilHitunganGejala7 = nilaiGejala7 * doubleGejala7;
                    double hasilHitunganGejala9 = nilaiGejala9 * doubleGejala9;
                    double hasilHitunganGejala2 = nilaiGejala2 * doubleGejala2;
                    double hasilHitunganGejala10 = nilaiGejala10 * doubleGejala10;

                    double Combine_CF4_CF13 = hasilHitunganGejala4 + hasilHitunganGejala13 * (1 - hasilHitunganGejala4);
                    double Combine_CFold_CF6_1 = Combine_CF4_CF13 + hasilHitunganGejala6 * (1 - Combine_CF4_CF13);
                    double Combine_CFold_CF7_1 = Combine_CFold_CF6_1 + hasilHitunganGejala7 * (1 - Combine_CFold_CF6_1);
                    double Combine_CFold_CF9_2 = Combine_CFold_CF7_1 + hasilHitunganGejala9 * (1 - Combine_CFold_CF7_1);
                    double Combine_CFold_CF2_1 = Combine_CFold_CF9_2 + hasilHitunganGejala2 * (1 - Combine_CFold_CF9_2);
                    double Combine_CFold_CF10_2 = Combine_CFold_CF2_1 + hasilHitunganGejala10 * (1 - Combine_CFold_CF2_1);

                    String hasilHitunganGejalaPenyakit4 = String.valueOf((Combine_CFold_CF10_2 * 100));

                    NamaPenyakit += "\nGastritis"+"\n"+hasilHitunganGejalaPenyakit4+" %";
                }

                if(chkGejala4.isChecked() && chkGejala14.isChecked() && chkGejala15.isChecked() && chkGejala7.isChecked() && chkGejala17.isChecked() && chkGejala18.isChecked() && chkGejala2.isChecked() && chkGejala19.isChecked()){
                    //nilai dari pakar
                    double nilaiGejala4 = 0.6;
                    double nilaiGejala14 = 0.6;
                    double nilaiGejala15 = 0.6;
                    double nilaiGejala7 = 0.8;
                    double nilaiGejala17 = 0.6;
                    double nilaiGejala18 = 0.8;
                    double nilaiGejala2 = 0.6;
                    double nilaiGejala19 = 0.8;
                    
                    //nilai dari user
                    double doubleGejala4 = Double.parseDouble(txtNilaiGejala4.getText().toString());
                    double doubleGejala14 = Double.parseDouble(txtNilaiGejala14.getText().toString());
                    double doubleGejala15 = Double.parseDouble(txtNilaiGejala15.getText().toString());
                    double doubleGejala7 = Double.parseDouble(txtNilaiGejala7.getText().toString());
                    double doubleGejala17 = Double.parseDouble(txtNilaiGejala17.getText().toString());
                    double doubleGejala18 = Double.parseDouble(txtNilaiGejala18.getText().toString());
                    double doubleGejala2 = Double.parseDouble(txtNilaiGejala2.getText().toString());
                    double doubleGejala19 = Double.parseDouble(txtNilaiGejala19.getText().toString());

                    double hasilHitunganGejala4 = nilaiGejala4 * doubleGejala4;
                    double hasilHitunganGejala14 = nilaiGejala14 * doubleGejala14;
                    double hasilHitunganGejala15 = nilaiGejala15 * doubleGejala15;
                    double hasilHitunganGejala7 = nilaiGejala7 * doubleGejala7;
                    double hasilHitunganGejala17 = nilaiGejala17 * doubleGejala17;
                    double hasilHitunganGejala18 = nilaiGejala18 * doubleGejala18;
                    double hasilHitunganGejala2 = nilaiGejala2 * doubleGejala2;
                    double hasilHitunganGejala19 = nilaiGejala19 * doubleGejala19;

                    double Combine_CF4_CF14 = hasilHitunganGejala4 + hasilHitunganGejala14 * (1 - hasilHitunganGejala4);
                    double Combine_CFold_CF15_1 = Combine_CF4_CF14 + hasilHitunganGejala15 * (1 - Combine_CF4_CF14);
                    double Combine_CFold_CF7_2 = Combine_CFold_CF15_1 + hasilHitunganGejala7 * (1 - Combine_CFold_CF15_1);
                    double Combine_CFold_CF17 = Combine_CFold_CF7_2 + hasilHitunganGejala17 * (1 - Combine_CFold_CF7_2);
                    double Combine_CFold_CF18 = Combine_CFold_CF17 + hasilHitunganGejala18 * (1 - Combine_CFold_CF17);
                    double Combine_CFold_CF2_2 = Combine_CFold_CF18 + hasilHitunganGejala2 * (1 - Combine_CFold_CF18);
                    double Combine_CFold_CF19 = Combine_CFold_CF2_2 + hasilHitunganGejala19 * (1 - Combine_CFold_CF2_2);

                    String hasilHitungGejalaPenyakit5 = String.valueOf((Combine_CFold_CF19 * 100));

                    NamaPenyakit += "\nGERD"+"\n"+hasilHitungGejalaPenyakit5+" %";
                }

                if(chkGejala20.isChecked() && chkGejala21.isChecked() && chkGejala22.isChecked()){
                    //nilai dari pakar
                    double nilaiGejala20 = 0.8;
                    double nilaiGejala21 = 0.6;
                    double nilaiGejala22 = 0.2;

                    //nilai dari user
                    double doubleGejala20 = Double.parseDouble(txtNilaiGejala20.getText().toString());
                    double doubleGejala21 = Double.parseDouble(txtNilaiGejala21.getText().toString());
                    double doubleGejala22 = Double.parseDouble(txtNilaiGejala22.getText().toString());

                    double hasilHitungGejala20 = nilaiGejala20 * doubleGejala20;
                    double hasilHitungGejala21 = nilaiGejala21 * doubleGejala21;
                    double hasilHitungGejala22 = nilaiGejala22 * doubleGejala22;

                    double Combine_CF20_CF21 = hasilHitungGejala20 + hasilHitungGejala21 * (1 - hasilHitungGejala20);
                    double Combine_CFold_CF22 = Combine_CF20_CF21 + hasilHitungGejala22 * (1 - Combine_CF20_CF21);

                    String hasilHitungGejalaPenyakit6 = String.valueOf((Combine_CFold_CF22 * 100));

                    NamaPenyakit += "\nKonstipasi/Sembelit"+"\n"+hasilHitungGejalaPenyakit6+" %";
                }

                if(chkGejala23.isChecked() && chkGejala6.isChecked() && chkGejala24.isChecked() && chkGejala25.isChecked() && chkGejala21.isChecked()){
                    //nilai dari pakar
                    double nilaiGejala23 = 0.8;
                    double nilaiGejala6 = 0.2;
                    double nilaiGejala24 = 0.2;
                    double nilaiGejala25 = 0.6;
                    double nilaiGejala21 = 0.4;

                    //nilai dari user
                    double doubleGejala23 = Double.parseDouble(txtNilaiGejala22.getText().toString());
                    double doubleGejala6 = Double.parseDouble(txtNilaiGejala6.getText().toString());
                    double doubleGejala24 = Double.parseDouble(txtNilaiGejala24.getText().toString());
                    double doubleGejala25 = Double.parseDouble(txtNilaiGejala25.getText().toString());
                    double doubleGejala21 = Double.parseDouble(txtNilaiGejala21.getText().toString());

                    double hasilHitunganGejala23 = nilaiGejala23 * doubleGejala23;
                    double hasilHitunganGejala6 = nilaiGejala6 * doubleGejala6;
                    double hasilHitunganGejala24 = nilaiGejala24 * doubleGejala24;
                    double hasilHitunganGejala25 = nilaiGejala25 * doubleGejala25;
                    double hasilHitunganGejala21 = nilaiGejala21 * doubleGejala21;

                    double Combine_CF23_CF6 = hasilHitunganGejala23 + hasilHitunganGejala6 * (1 - hasilHitunganGejala23);
                    double Combine_CFold_CF24 = Combine_CF23_CF6 + hasilHitunganGejala24 * (1 - Combine_CF23_CF6);
                    double Combine_CFold_CF25 = Combine_CFold_CF24 + hasilHitunganGejala25 * (1 - Combine_CFold_CF24);
                    double Combine_CFold_CF21 = Combine_CFold_CF25 + hasilHitunganGejala21 * (1 - Combine_CFold_CF25);

                    String hasilHitungGejalaPenyakit7 = String.valueOf((Combine_CFold_CF21 * 100));

                    NamaPenyakit += "\nUsus Buntu"+"\n"+hasilHitungGejalaPenyakit7+" %";
                }

                if(chkGejala4.isChecked() && chkGejala12.isChecked() && chkGejala13.isChecked() && chkGejala6.isChecked() && chkGejala15.isChecked() && chkGejala7.isChecked() && chkGejala16.isChecked() && chkGejala17.isChecked()){
                    //nilai dari pakar
                    double nilaiGejala4 = 0.6;
                    double nilaiGejala12 = 0.8;
                    double nilaiGejala13 = 0.8;
                    double nilaiGejala6 = 0.8;
                    double nilaiGejala15 = 0.6;
                    double nilaiGejala7 = 0.6;
                    double nilaiGejala16 = 0.6;
                    double nilaiGejala17 = 0.6;

                    //nilai dari user
                    double doubleGejala4 = Double.parseDouble(txtNilaiGejala4.getText().toString());
                    double doubleGejala12 = Double.parseDouble(txtNilaiGejala12.getText().toString());
                    double doubleGejala13 = Double.parseDouble(txtNilaiGejala13.getText().toString());
                    double doubleGejala6 = Double.parseDouble(txtNilaiGejala6.getText().toString());
                    double doubleGejala15 = Double.parseDouble(txtNilaiGejala15.getText().toString());
                    double doubleGejala7 = Double.parseDouble(txtNilaiGejala7.getText().toString());
                    double doubleGejala16 = Double.parseDouble(txtNilaiGejala16.getText().toString());
                    double doubleGejala17 = Double.parseDouble(txtNilaiGejala17.getText().toString());

                    double hasilHitungGejala4 = nilaiGejala4 * doubleGejala4;
                    double hasilHitungGejala12 = nilaiGejala12 * doubleGejala12;
                    double hasilHitungGejala13 = nilaiGejala13 * doubleGejala13;
                    double hasilHitungGejala6 = nilaiGejala6 * doubleGejala6;
                    double hasilHitungGejala15 = nilaiGejala15 * doubleGejala15;
                    double hasilHitungGejala7 = nilaiGejala7 * doubleGejala7;
                    double hasilHitungGejala16 = nilaiGejala16 * doubleGejala16;
                    double hasilHitungGejala17 = nilaiGejala17 * doubleGejala17;

                    double Combine_CF4_CF12_1 = hasilHitungGejala4 + hasilHitungGejala12 * (1 - hasilHitungGejala4);
                    double Combine_CFold_CF13_1 = Combine_CF4_CF12_1 + hasilHitungGejala13 * (1 - Combine_CF4_CF12_1);
                    double Combine_CFold_CF6_2 = Combine_CFold_CF13_1 + hasilHitungGejala6 * (1 - Combine_CFold_CF13_1);
                    double Combine_CFold_CF15_2 = Combine_CFold_CF6_2 + hasilHitungGejala15 * (1 - Combine_CFold_CF6_2);
                    double Combine_CFold_CF7_3 = Combine_CFold_CF15_2 + hasilHitungGejala7 * (1 - Combine_CFold_CF15_2);
                    double Combine_CFold_CF16_1 = Combine_CFold_CF7_3 + hasilHitungGejala16 * (1 - Combine_CFold_CF7_3);
                    double Combine_CFold_CF17_1 = Combine_CFold_CF16_1 + hasilHitungGejala17 * (1 - Combine_CFold_CF16_1);

                    String hasilHitungGejalaPenyakit8 = String.valueOf((Combine_CFold_CF17_1 * 100));

                    NamaPenyakit += "\nDispepsia"+"\n"+hasilHitungGejalaPenyakit8+" %";
                }

                tvOutput.setText(""+NamaPenyakit);
            }
        });

    }
}

activity_main.xml

<?xml version="1.0" encoding="utf-8"?>
<ScrollView
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:scrollbars="vertical"
    android:padding="10dp"
    tools:context=".MainActivity">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:orientation="vertical">

        <ImageView
            android:id="@+id/imageView"
            android:layout_width="wrap_content"
            android:layout_height="102dp"
            app:srcCompat="@drawable/labeldeteksi" />

        <TextView
            android:id="@+id/textView2"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Cara pengisian isi checkbox pada gejala yang anda rasakan. Dan masukan nilai jawaban anda" />

        <TextView
            android:id="@+id/textView3"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Skala nilai jawaban" />

        <TextView
            android:id="@+id/textView4"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="0 = Tidak" />

        <TextView
            android:id="@+id/textView5"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="0.2 = Tidak Tahu" />

        <TextView
            android:id="@+id/textView6"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="0.4 = Kurang Yakin" />

        <TextView
            android:id="@+id/textView7"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="0.6 = Cukup Yakin" />

        <TextView
            android:id="@+id/textView8"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="0.8 = Yakin" />

        <TextView
            android:id="@+id/textView9"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="1 = Sangat Yakin" />

        <CheckBox
            android:id="@+id/checkBox"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="1. Sering buang air besar" />

        <AutoCompleteTextView
            android:id="@+id/autoCompleteTextView"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Masukan Jawaban Anda" />

        <CheckBox
            android:id="@+id/checkBox2"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="2. Mengalami masalah pencernaan dan perubahaan feses" />

        <AutoCompleteTextView
            android:id="@+id/autoCompleteTextView2"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Masukan Jawaban Anda" />

        <CheckBox
            android:id="@+id/checkBox3"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="3. Demam tinggi (>40 oC)" />

        <AutoCompleteTextView
            android:id="@+id/autoCompleteTextView3"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Masukan Jawaban Anda" />

        <CheckBox
            android:id="@+id/checkBox4"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="4. Perut terasa kembung" />

        <AutoCompleteTextView
            android:id="@+id/autoCompleteTextView4"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Masukan Jawaban Anda" />

        <CheckBox
            android:id="@+id/checkBox5"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="5. Dehidrasi" />

        <AutoCompleteTextView
            android:id="@+id/autoCompleteTextView5"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Masukan Jawaban Anda" />

        <CheckBox
            android:id="@+id/checkBox6"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="6. Mual dan muntah" />

        <AutoCompleteTextView
            android:id="@+id/autoCompleteTextView6"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Masukan Jawaban Anda" />

        <CheckBox
            android:id="@+id/checkBox7"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="7. Nyeri atau ketidaknyamanan di perut bagian atas" />

        <AutoCompleteTextView
            android:id="@+id/autoCompleteTextView7"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Masukan Jawaban Anda" />

        <CheckBox
            android:id="@+id/checkBox8"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="8. Pusing dan Demam" />

        <AutoCompleteTextView
            android:id="@+id/autoCompleteTextView8"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Masukan Jawaban Anda" />

        <CheckBox
            android:id="@+id/checkBox9"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="9. Nyeri di dada" />

        <AutoCompleteTextView
            android:id="@+id/autoCompleteTextView9"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Masukan Jawaban Anda" />

        <CheckBox
            android:id="@+id/checkBox10"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="10. Nafsu makan menurun dan penurunan berat badan" />

        <AutoCompleteTextView
            android:id="@+id/autoCompleteTextView10"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Masukan Jawaban Anda" />

        <CheckBox
            android:id="@+id/checkBox11"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="11. Mudah lelah" />

        <AutoCompleteTextView
            android:id="@+id/autoCompleteTextView11"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Masukan Jawaban Anda" />

        <CheckBox
            android:id="@+id/checkBox12"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="12. Mengalami rasa sakit di perut" />

        <AutoCompleteTextView
            android:id="@+id/autoCompleteTextView12"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Masukan Jawaban Anda" />

        <CheckBox
            android:id="@+id/checkBox13"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="13. Mudah kenyang" />

        <AutoCompleteTextView
            android:id="@+id/autoCompleteTextView13"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Masukan Jawaban Anda" />

        <CheckBox
            android:id="@+id/checkBox14"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="14. Timbul pendarahan di perut" />

        <AutoCompleteTextView
            android:id="@+id/autoCompleteTextView14"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Masukan Jawaban Anda" />

        <CheckBox
            android:id="@+id/checkBox15"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="15. Sering bersendawa" />

        <AutoCompleteTextView
            android:id="@+id/autoCompleteTextView15"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Masukan Jawaban Anda" />

        <CheckBox
            android:id="@+id/checkBox16"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="16. Merasa panas di dada dan diperut" />

        <AutoCompleteTextView
            android:id="@+id/autoCompleteTextView16"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Masukan Jawaban Anda" />

        <CheckBox
            android:id="@+id/checkBox17"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="17. Mulut terasa asam" />

        <AutoCompleteTextView
            android:id="@+id/autoCompleteTextView17"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Masukan Jawaban Anda" />

        <CheckBox
            android:id="@+id/checkBox18"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="18. Merasa sakit dan tidak nyaman ketika menelan" />

        <AutoCompleteTextView
            android:id="@+id/autoCompleteTextView18"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Masukan Jawaban Anda" />

        <CheckBox
            android:id="@+id/checkBox19"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="19. Sering batuk-batuk" />

        <AutoCompleteTextView
            android:id="@+id/autoCompleteTextView19"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Masukan Jawaban  Anda" />

        <CheckBox
            android:id="@+id/checkBox20"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="20. Jarang buang air besar" />

        <AutoCompleteTextView
            android:id="@+id/autoCompleteTextView20"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Masukan Jawaban Anda" />

        <CheckBox
            android:id="@+id/checkBox21"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="21. Feses keras" />

        <AutoCompleteTextView
            android:id="@+id/autoCompleteTextView21"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Masukan Jawaban Anda" />

        <CheckBox
            android:id="@+id/checkBox22"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="22. Sering buang angin" />

        <AutoCompleteTextView
            android:id="@+id/autoCompleteTextView22"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Masukan Jawaban Anda" />

        <CheckBox
            android:id="@+id/checkBox23"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="23. Nyeri perut pada bagian kanan bawah" />

        <AutoCompleteTextView
            android:id="@+id/autoCompleteTextView23"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Masukan Jawaban Anda" />

        <CheckBox
            android:id="@+id/checkBox24"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="24. Demam ringan (37oC - 39 oC)" />

        <AutoCompleteTextView
            android:id="@+id/autoCompleteTextView24"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Masukan Jawaban Anda" />

        <CheckBox
            android:id="@+id/checkBox25"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="25. Terasa tegang pada otot perut" />

        <AutoCompleteTextView
            android:id="@+id/autoCompleteTextView25"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Masukan Jawaban Anda" />

        <ImageButton
            android:id="@+id/imageButton"
            android:layout_width="280dp"
            android:layout_height="65dp"
            android:layout_marginLeft="25dp"
            app:srcCompat="@drawable/buttonperiksa" />

        <TextView
            android:id="@+id/textView"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Hasil"
            android:textAlignment="center"
            android:textSize="28sp"
            android:textStyle="bold" />

    </LinearLayout>

</ScrollView>

MenuInformasi.java

package com.example.sistempakarpencernaan;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.ImageButton;

public class MenuInformasi extends AppCompatActivity {
    private ImageButton imgbtni1, imgbtni2, imgbtni3, imgbtni4, imgbtni5, imgbtni6, imgbtni7, imgbtni8;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_menu_informasi);

        imgbtni1 = (ImageButton) findViewById(R.id.imageButtonI1);
        imgbtni1.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                openIsiDiare();
            }
        });

        imgbtni2 = (ImageButton) findViewById(R.id.imageButtonI2);
        imgbtni2.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                openIsiGastroenteritis();
            }
        });

        imgbtni3 = (ImageButton) findViewById(R.id.imageButtonI3);
        imgbtni3.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                openIsiTukaklambung();
            }
        });

        imgbtni4 = (ImageButton) findViewById(R.id.imageButtonI4);
        imgbtni4.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                openIsiGastritis();
            }
        });

        imgbtni5 = (ImageButton) findViewById(R.id.imageButtonI5);
        imgbtni5.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                openIsiGerd();
            }
        });

        imgbtni6 = (ImageButton) findViewById(R.id.imageButtonI6);
        imgbtni6.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                openIsiKonstipasi();
            }
        });

        imgbtni7 = (ImageButton) findViewById(R.id.imageButtonI7);
        imgbtni7.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                openIsiUsusbuntu();
            }
        });

        imgbtni8 = (ImageButton) findViewById(R.id.imageButtonI8);
        imgbtni8.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                openIsiDispepsia();
            }
        });
    }

    public void openIsiDiare(){
        Intent intentI1 = new Intent(this,IsiMenuDiare.class);
        startActivity(intentI1);
    }
    public void openIsiGastroenteritis(){
        Intent intentI2 = new Intent(this, IsiMenuGastroenteritis.class);
        startActivity(intentI2);
    }
    public void openIsiTukaklambung(){
        Intent intentI3 = new Intent(this, IsiMenuTukaklambung.class);
        startActivity(intentI3);
    }
    public void openIsiGastritis(){
        Intent intentI4 = new Intent(this, IsiMenuGastritis.class);
        startActivity(intentI4);
    }
    public void openIsiGerd(){
        Intent intentI5 = new Intent(this, IsiMenuGerd.class);
        startActivity(intentI5);
    }
    public void openIsiKonstipasi(){
        Intent intentI6 = new Intent(this, IsiMenuKonstipasi.class);
        startActivity(intentI6);
    }
    public void openIsiUsusbuntu(){
        Intent intentI7 = new Intent(this, IsiMenuUsusbuntu.class);
        startActivity(intentI7);
    }
    public void openIsiDispepsia(){
        Intent intentI8 = new Intent(this, IsiMenuDispepsia.class);
        startActivity(intentI8);
    }
}

activity_menu_informasi.xml

<?xml version="1.0" encoding="utf-8"?>
<ScrollView
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/backgroundbasic4"
    tools:context=".MenuInformasi">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical">
        <ImageView
            android:id="@+id/imageView2"
            android:layout_width="wrap_content"
            android:layout_height="102dp"
            android:layout_weight="1"
            app:srcCompat="@drawable/labelinformasi" />

    <RelativeLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content">

        <ImageButton
            android:id="@+id/imageButtonI1"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginTop="30dp"
            android:layout_marginLeft="40dp"
            app:srcCompat="@drawable/buttondiare2" />

        <ImageButton
            android:id="@+id/imageButtonI2"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginTop="140dp"
            android:layout_marginLeft="40dp"
            app:srcCompat="@drawable/buttongastroente2" />

        <ImageButton
            android:id="@+id/imageButtonI3"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginTop="250dp"
            android:layout_marginLeft="40dp"
            app:srcCompat="@drawable/buttontukak2" />

        <ImageButton
            android:id="@+id/imageButtonI4"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginTop="360dp"
            android:layout_marginLeft="40dp"
            app:srcCompat="@drawable/buttongastritis2" />

        <ImageButton
            android:id="@+id/imageButtonI5"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginTop="470dp"
            android:layout_marginLeft="40dp"
            app:srcCompat="@drawable/buttongerd2" />

        <ImageButton
            android:id="@+id/imageButtonI6"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginTop="580dp"
            android:layout_marginLeft="40dp"
            app:srcCompat="@drawable/buttonkonstipasi2" />

        <ImageButton
            android:id="@+id/imageButtonI7"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginTop="690dp"
            android:layout_marginLeft="40dp"
            app:srcCompat="@drawable/buttonususbuntu2" />

        <ImageButton
            android:id="@+id/imageButtonI8"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginTop="800dp"
            android:layout_marginLeft="40dp"
            app:srcCompat="@drawable/buttondispepsia2" />
    </RelativeLayout>
    </LinearLayout>
</ScrollView>

activity_isi_menu_diare.xml

<?xml version="1.0" encoding="utf-8"?>
<ScrollView
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/isiinfdiare"
    tools:context=".IsiMenuDiare">

</ScrollView>

activity_isi_menu_gastroenteritis.xml

<?xml version="1.0" encoding="utf-8"?>
<ScrollView
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/isiinfgastroenteritis"
    tools:context=".IsiMenuGastroenteritis">

</ScrollView>

activity_isi_menu_tukaklambnng.xml

<?xml version="1.0" encoding="utf-8"?>
<ScrollView
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/isiinftukaklambung"
    tools:context=".IsiMenuTukaklambung">

</ScrollView>

activity_isi_menu_gastritis.xml

<?xml version="1.0" encoding="utf-8"?>
<ScrollView
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/isiinfgastritis"
    tools:context=".IsiMenuGastritis">

</ScrollView>

activity_isi_menu_gerd.xml

<?xml version="1.0" encoding="utf-8"?>
<ScrollView
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/isiinfgerd"
    tools:context=".IsiMenuGerd">

</ScrollView>

activity_isi_menu_konstipasi.xml

<?xml version="1.0" encoding="utf-8"?>
<ScrollView
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/isiinfkonstipasi"
    tools:context=".IsiMenuKonstipasi">

</ScrollView>

activity_isi_menu_ususbuntu.xml

<?xml version="1.0" encoding="utf-8"?>
<ScrollView
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/isiinfususubuntu"
    tools:context=".IsiMenuUsusbuntu">

</ScrollView>

activity_isi_menu_dispepsia.xml

<?xml version="1.0" encoding="utf-8"?>
<ScrollView
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/isiinfdispepsia"
    tools:context=".IsiMenuDispepsia">

</ScrollView>

MenuTips.java

package com.example.sistempakarpencernaan;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;

public class MenuTips extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_menu_tips);
    }
}

activity_menu_tips.xml

<?xml version="1.0" encoding="utf-8"?>
<ScrollView
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/labelisi"
    tools:context=".MenuTips">

</ScrollView>

QuizActivity.java

package com.example.sistempakarpencernaan;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;
import android.widget.Toast;

public class QuizActivity extends AppCompatActivity {

    private QuestionBank mQuestionLibrary = new QuestionBank();
    private TextView mScoreView, mQuestionView;
    private Button mButtonChoice1, mButtonChoice2, mButtonChoice3, mButtonChoice4;
    private String mAnswer;
    private int mScore = 0;
    private int mQuestionNumber = 0;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_quiz);
        //
        mScoreView = (TextView) findViewById(R.id.score);
        mQuestionView = (TextView) findViewById(R.id.pertanyaan);
        mButtonChoice1 = (Button) findViewById(R.id.choice1);
        mButtonChoice2 = (Button) findViewById(R.id.choice2);
        mButtonChoice3 = (Button) findViewById(R.id.choice3);
        mButtonChoice4 = (Button) findViewById(R.id.choice4);
        updateQuestion();

        updateScore(mScore);
    }
    private void updateQuestion(){
        //
        if(mQuestionNumber<mQuestionLibrary.getLength() ){
            mQuestionView.setText(mQuestionLibrary.getQuestion(mQuestionNumber));
            mButtonChoice1.setText(mQuestionLibrary.getChoice(mQuestionNumber, 1));
            mButtonChoice2.setText(mQuestionLibrary.getChoice(mQuestionNumber, 2));
            mButtonChoice3.setText(mQuestionLibrary.getChoice(mQuestionNumber, 3));
            mButtonChoice4.setText(mQuestionLibrary.getChoice(mQuestionNumber, 4));
            mAnswer = mQuestionLibrary.getCorrectAnswer(mQuestionNumber);
            mQuestionNumber++;
        }
        else{
            Toast.makeText(QuizActivity.this, "It was last question", Toast.LENGTH_SHORT).show();
            Intent intent = new Intent(QuizActivity.this, HighestScoreActivity.class);
            intent.putExtra("score", mScore);
            startActivity(intent);
        }
    }
    private void updateScore(int point){
        mScoreView.setText(""+mScore+"/"+mQuestionLibrary.getLength());
    }

    public void onClick(View view){
        Button answer = (Button) view;
        if (answer.getText() == mAnswer){
            mScore = mScore+1;
            Toast.makeText(QuizActivity.this, "Benar", Toast.LENGTH_SHORT).show();
        } else
            Toast.makeText(QuizActivity.this, "Salah", Toast.LENGTH_SHORT).show();
        updateScore(mScore);
        updateQuestion();
    }
}

QuestionBank.java

package com.example.sistempakarpencernaan;

public class QuestionBank {

    private String textQuestion [] = {
            "1. Mulut, Kerongkongan, Lambung, Usus Halus, Usus Besar, Rektum, dan Anus Merupakan organ?",
            "2. Berikut yang termasuk penyakit pada lambung, kecuali?",
            "3. Penyakit sembelit disebut juga dengan?",
            "4. Penyakit gastritis menyerang organ?",
            "5. Infeksi Bakteri Helicobacter pylori yang terjadi pada lambung menyebabkan penyakit?",
            "6. Appendix biasa disebut dengan?",
            "7. Gastroesophageal refluk diseae disebut dengan?",
            "8. Organ yang memproduksi asam lambung?",
            "9. Nama proses pembedahan usus buntu adalah?",
            "10. Berikut adalah cara menjaga pencernaan anda, kecuali?"
    };

    //array untuk jawaban
    private String multipleChoice [][] = {
            {"Sistem Pencernaan", "Sistem Pernapasan", "Sistem Peredaran Darah", "Sistem Imun"},
            {"GERD", "Tukak Lambung", "Usus Buntu", "Gastritis"},
            {"Diare", "Tukak Lambung", "Konstipasi", "Gastritis"},
            {"Usus Halus", "Lambung", "Mulut", "Kerongkongan"},
            {"Usus Buntu", "Sembelit", "Konstipasi", "Tukak Lambung"},
            {"Radang", "Diare", "Usus Buntu", "GERD"},
            {"GERD", "Tukak Lambung", "Konstipasi", "Gastritis"},
            {"Usus Halus", "Lambung", "Mulut", "Kerongkongan"},
            {"Antibiotik", "Laparoskopi", "Patologis", "Endoskopi"},
            {"Rutin Olahraga", "Rajin Minum Air putih", "Makanan bernutrisi", "Konsumsi makanan pedas, dan asam"},

    };

    private String mCorrectAnswers[] = {"Sistem Pencernaan", "Usus Buntu", "Konstipasi", "Lambung", "Tukak Lambung", "Usus Buntu", "GERD", "Lambung", "Laparoskopi", "Konsumsi makanan pedas, dan asam"};

    public int getLength() {
        return textQuestion.length;
    }

    public String getQuestion(int a){
        String question = textQuestion[a];
        return question;
    }

    public String getChoice(int index, int num){
        String choice = multipleChoice[index][num-1];
        return choice;
    }

    public String getCorrectAnswer (int a){
        String answer = mCorrectAnswers[a];
        return answer;
    }
}

HighestScoreActivity.java

package com.example.sistempakarpencernaan;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.content.SharedPreferences;
import android.os.Bundle;
import android.view.View;
import android.widget.TextView;

import org.w3c.dom.Text;

public class HighestScoreActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_highest_score);

        TextView txtScore = (TextView) findViewById(R.id.textScore);
        TextView txtHighScore = (TextView) findViewById(R.id.textHighScore);
        Intent intent = getIntent();
        int score = intent.getIntExtra("score",0);
        txtScore.setText("Skor Kamu: "+score);

        SharedPreferences mypref = getPreferences(MODE_PRIVATE);
        int highscore = mypref.getInt("highscore", 0);
        if(highscore>=score)
            txtHighScore.setText("High Score: " + highscore);
        else
        {
            txtHighScore.setText("New Highscore: "+score);
            SharedPreferences.Editor editor = mypref.edit();
            editor.putInt("highscore", score);
            editor.commit();
        }
    }

    public void onClick (View view){
        Intent intent = new Intent(HighestScoreActivity.this, QuizActivity.class);
        startActivity(intent);
    }
}

activity_quiz.xml

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:background="@drawable/bgbasic"
    android:paddingBottom="15dp"
    android:paddingTop="15dp"
    android:paddingLeft="15dp"
    android:paddingRight="15dp"
    tools:context=".QuizActivity">

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Pertanyaan Quiz"
        android:textSize="20sp"
        android:padding="3dp"
        android:layout_marginBottom="10dp"
        android:id="@+id/pertanyaan"/>
    <Button
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="A"
        android:background="#11b1e5"
        android:textColor="#ffffff"
        android:padding="5dp"
        android:layout_marginBottom="20dp"
        android:onClick="onClick"
        android:id="@+id/choice1"/>
    <Button
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="B"
        android:background="#11b1e5"
        android:textColor="#ffffff"
        android:padding="5dp"
        android:layout_marginBottom="20dp"
        android:onClick="onClick"
        android:id="@+id/choice2"/>
    <Button
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="C"
        android:background="#11b1e5"
        android:textColor="#ffffff"
        android:padding="5dp"
        android:layout_marginBottom="20dp"
        android:onClick="onClick"
        android:id="@+id/choice3"/>
    <Button
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="D"
        android:background="#11b1e5"
        android:textColor="#ffffff"
        android:padding="5dp"
        android:layout_marginBottom="20dp"
        android:onClick="onClick"
        android:id="@+id/choice4"/>

    <RelativeLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:padding="6dp"
        android:layout_gravity="center_horizontal"
        android:layout_marginBottom="20dp"
        android:background="#fdb22f">

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:id="@+id/score_test"
            android:textSize="20sp"
            android:layout_centerHorizontal="true"
            android:textColor="#ffffff"
            android:textStyle="bold"
            android:text="Score"/>

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:id="@+id/score"
            android:textSize="15sp"
            android:layout_centerHorizontal="true"
            android:layout_below="@id/score_test"
            android:textColor="#ffffff"
            android:text="0/0"/>

    </RelativeLayout>
</LinearLayout>

activity_highest_score.xml

<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:id="@+id/activity_highest_score"
    android:paddingRight="15dp"
    android:paddingLeft="15dp"
    android:paddingTop="15dp"
    android:paddingBottom="15dp"
    tools:context=".HighestScoreActivity">

    <LinearLayout
        android:orientation="vertical"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:layout_marginTop="107dp">
        <TextView
            android:layout_width="500dp"
            android:layout_height="wrap_content"
            android:id="@+id/textScore"
            android:background="#11b1e5"
            android:textColor="#ffffff"
            android:padding="15dp"
            android:text="Skor Anda:"/>

        <TextView
            android:layout_width="500dp"
            android:layout_height="wrap_content"
            android:id="@+id/textHighScore"
            android:background="#fdb22f"
            android:textColor="#ffffff"
            android:padding="15dp"
            android:text="Skor Tertinggi:"/>

        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Coba Lagi"
            android:layout_gravity="center_horizontal"
            android:onClick="onClick"
            android:id="@+id/buttonlagi"/>

    </LinearLayout>
</RelativeLayout>

MenuTentang.java

package com.example.sistempakarpencernaan;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;

public class MenuTentang extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_menu_tentang);
    }
}

activity_menu_tentang.xml

<?xml version="1.0" encoding="utf-8"?>
<ScrollView
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/menutentangbackground"
    tools:context=".MenuTentang">

</ScrollView>

colours.xml

<?xml version="1.0" encoding="utf-8"?>
<resources>
    <color name="purple_200">#FFBB86FC</color>
    <color name="purple_500">#FF6200EE</color>
    <color name="purple_700">#FF3700B3</color>
    <color name="teal_200">#FF03DAC5</color>
    <color name="teal_700">#FF018786</color>
    <color name="atas">#1eb6ec</color>
    <color name="black">#FF000000</color>
    <color name="white">#FFFFFFFF</color>
</resources>

strings.xml

<resources>
    <string name="app_name">Sistem Pakar Pencernaan</string>
</resources>
