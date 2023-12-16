# PRACTICA-2-SENSOR-DHT22
Este repositorio muestra como podemos programar una ESP32 con el sensor DHT11
 # Introducción
 ## DESCRIPCION 
 La Esp32 la utilizamos en un entorno de adquision de datos, lo cual en esta practica ocuparemos un sensor (DTH11) para adquirir temperatura y humedad del entorno; Cabe aclarar que esta practica se usara un simulador llamado WOKWI.
 ## Material Necesario
 Para realizar esta practica necesitas lo siguiente

°WOKWI

°Tarjeta ESP 32

°Sensor DHT11
 # Instrucciones
 ## Requisitos previos
 Para poder usar este repositorio necesitas entrar a la plataforma WOKWI.
 ## Instrucciones de preparación de entorno
 1.Abrir la terminal de programación y colocar la siguente programación:
 
#include "DHTesp.h"
#include <LiquidCrystal_I2C.h>

const int DHT_PIN = 15;
DHTesp dhtSensor;

## 2.Instalar la libreria de DHT sensor library for ESPx como se muestra en la siguente imagen.

![(![image](https://github.com/ErickRomeroRamos/PRACTICA-2-SENSOR-DHT22/assets/153964793/00855d4d-6088-476b-8cfd-71dcab45cee7)

 ## 3.Hacer la conexion de DHT11 con la ESP32 como se muestra en la siguente imagen.


 

void setup() {

  Serial.begin(115200);
  dhtSensor.setup(DHT_PIN, DHTesp::DHT22);
}

void loop() {

  TempAndHumidity  data = dhtSensor.getTempAndHumidity();
  Serial.println("Temp: " + String(data.temperature, 1) + "°C");
  Serial.println("Humidity: " + String(data.humidity, 1) + "%");
  Serial.println("---");
  delay(1000);
}
