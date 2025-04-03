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


           

