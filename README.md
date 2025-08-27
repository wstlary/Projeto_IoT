# Tutorial Montagem Servo/Motor | ESP-32 - Passo a Passo

### 1️⃣ Passo 1  
![Passo 1](Servo_Motor/foto1.jpg)

### 2️⃣ Passo 2  
![Passo 2](Servo_Motor/foto2.jpg)

### 3️⃣ Passo 3  
![Passo 3](Servo_Motor/foto3.jpg)

### 4️⃣ Passo 4  
![Passo 4](Servo_Motor/foto4.jpg)

### 5️⃣ Passo 5  
![Passo 5](Servo_Motor/foto5.jpg)

### 6️⃣ Passo 6  
![Passo 6](Servo_Motor/foto6.jpg)

### 7️⃣ Passo 7  
![Passo 7](Servo_Motor/foto7.jpg)

### 8️⃣ Passo 8  
![Passo 8](Servo_Motor/foto8.jpg)

### 🏁 Passo 9 — Resultado Final   
![Passo 9](Servo_Motor/foto9.jpg)


### 💻 Código - Servo/Motor para Arduino IDE:

```cpp
#include <ESP32Servo.h>

Servo meuServo;

void setup() {
  meuServo.setPeriodHertz(50);
  meuServo.attach(14);
}

void loop() {
  meuServo.write(180);
  delay(1000);

  meuServo.write(90);
  delay(1000);

  meuServo.write(0);
  delay(1000);

  meuServo.write(90);
  delay(1000);

  meuServo.write(180);
  delay(1000);
}

```

---

# Tutorial Montagem DHT/Temperatura | ESP-32 - Passo a Passo

### 1️⃣ Passo 1  
![Passo 1](DHT/foto1.jpg)

### 2️⃣ Passo 2  
![Passo 2](DHT/foto2.jpg)

### 3️⃣ Passo 3  
![Passo 3](DHT/foto3.jpg)

### 4️⃣ Passo 4  
![Passo 4](DHT/foto4.jpg)

### 5️⃣ Passo 5  
![Passo 5](DHT/foto5.jpg)

### 6️⃣ Passo 6  
![Passo 6](DHT/foto6.jpg)

### 7️⃣ Passo 7  
![Passo 7](DHT/foto7.jpg)

### 8️⃣ Passo 8  
![Passo 8](DHT/foto8.jpg)

### 9️⃣ Passo 9 
![Passo 9](DHT/foto9.jpg)

### 🔟  Passo 10  
![Passo 10](DHT/foto10.jpg)

### 🏁 Passo 11 — Resultado Final 
![Passo 11](DHT/foto11.jpg)

### 💻 Código - DHT/Temperatura para Arduino IDE:

```cpp

#include <Bonezegei_DHT11.h>

Bonezegei_DHT11 dht(2);

const int LED_VERDE = 18;
const int LED_VERMELHO = 5;

void setup() {
  Serial.begin(115200);
  dht.begin();

  pinMode(LED_VERDE, OUTPUT);
  pinMode(LED_VERMELHO, OUTPUT);
}

void loop() {

  if (dht.getData()) {
    float tempC = dht.getTemperature();
    float tempF = dht.getTemperature(true);
    int hum = dht.getHumidity();

    Serial.print("Temp: ");
    Serial.print(tempC);
    Serial.print(" °C / ");
    Serial.print(tempF);
    Serial.print(" °F | Humidity: ");
    Serial.print(hum);
    Serial.println(" %");
  }

  if (dht.getTemperature() < 23) {
    digitalWrite(LED_VERDE, LOW);
    digitalWrite(LED_VERMELHO, HIGH);
  } else {
    digitalWrite(LED_VERDE, HIGH);
    digitalWrite(LED_VERMELHO, LOW);
  }

  delay(2000);
}


```
