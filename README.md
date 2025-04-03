# CalculadoraIMC-NP1

Parte do XML


<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp">

    <EditText
        android:id="@+id/editPeso"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Peso (Kg)"
        android:inputType="numberDecimal" />

    <EditText
        android:id="@+id/editAltura"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Altura (m)"
        android:inputType="numberDecimal"/>

    <Button
        android:id="@+id/btnCalcular"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Calcular IMC"
        android:layout_gravity="center"
        />

    <TextView
        android:id="@+id/textResultado"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_gravity="center"
        android:text="Resultado aparecera aqui"
        android:textSize="18sp" />

</LinearLayout>

/////////////////////////////////

Parte do Java


package com.Pedroh.calculadoraimc;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import java.util.Locale;
import androidx.appcompat.app.AppCompatActivity;
public class MainActivity extends AppCompatActivity {
   @Override
   protected void onCreate(Bundle savedInstanceState) {
     super.onCreate(savedInstanceState);
     setContentView(R.layout.activity_main);
     EditText editPeso = findViewById(R.id.editPeso);
     EditText editAltura = findViewById(R.id.editAltura);
     Button btnCalcular = findViewById(R.id.btnCalcular);
     TextView textResultado = findViewById(R.id.textResultado);
     btnCalcular.setOnClickListener(new View.OnClickListener(){
        @Override
        public void onClick(View v) {
            String pesoStr = editPeso.getText().toString();
            String alturaStr = editAltura.getText().toString();
            if (pesoStr.isEmpty() || alturaStr.isEmpty()) {
                textResultado.setText("Preencha todos os campos!");
                return;
            }
            float peso = Float.parseFloat(pesoStr);
            float altura = Float.parseFloat(alturaStr);
            float imc = peso / (altura * altura);
            textResultado.setText("Seu IMC é: " + String.format(Locale.US,"%.2f",imc));

        }
    });
   }
}


