# 🤖 Robô Sumô – ESP32 + BTS7960

<img width="795" height="562" alt="image" src="https://github.com/user-attachments/assets/1314b640-ad28-4648-a65f-a59f920bc5d5" />


## 🎯 Objetivo  
Construir um robô sumô com:  
- Controle via Bluetooth  
- Dois drivers BTS7960  
- Motores de vidro elétrico  
- Conversor DC/DC
- Bateria 5Ah

---

## 🛠 Tecnologias  
- ESP32  
- Bluetooth Serial  
- PWM  

---

## ⚙ Arquitetura
[ESP32] → [BTS7960] → [Motores]
↓
[Bluetooth App]

---

## 📐 Desenhos técnicos
<img width="1255" height="878" alt="image" src="https://github.com/user-attachments/assets/f3082b6c-9ab9-4f79-a685-ecdb7eea465a" />
<img width="1255" height="886" alt="image" src="https://github.com/user-attachments/assets/a16ed5b9-88b9-467d-ab54-355e8d38b71b" />
<img width="1257" height="876" alt="image" src="https://github.com/user-attachments/assets/3f731633-7829-46ac-94b7-b3b759e4dc85" />
<img width="1248" height="884" alt="image" src="https://github.com/user-attachments/assets/67d9b2f7-d9c2-4e23-82ee-adb404c047a6" />
<img width="1252" height="883" alt="image" src="https://github.com/user-attachments/assets/747b7482-72d3-412d-a841-87652d26deeb" />
<img width="1249" height="888" alt="image" src="https://github.com/user-attachments/assets/b26fd955-7390-40cb-b257-0ad4a3bd08f0" />
<img width="1255" height="886" alt="image" src="https://github.com/user-attachments/assets/66d43678-11bb-48aa-918d-684b8af4a58d" />
<img width="1254" height="883" alt="image" src="https://github.com/user-attachments/assets/6027daf1-a502-4311-9900-b3eba709327e" />


## 💻 Código base (movimentação)

```cpp
// -------- MOTOR A (Direito) --------
#define A_RPWM 25
#define A_LPWM 26
#define A_REN 18
#define A_LEN 5
// -------- MOTOR B (Esquerdo) --------
#define B_RPWM 27
#define B_LPWM 22
#define B_REN 32
#define B_LEN 33
// Bluetooth
#include "BluetoothSerial.h"
BluetoothSerial SerialBT;
char comando = 'S';
void setup() {
SerialBT.begin("Overtorq");
pinMode(A_RPWM, OUTPUT);
pinMode(A_LPWM, OUTPUT);
21
pinMode(A_REN, OUTPUT);
pinMode(A_LEN, OUTPUT);
pinMode(B_RPWM, OUTPUT);
pinMode(B_LPWM, OUTPUT);
pinMode(B_REN, OUTPUT);
pinMode(B_LEN, OUTPUT);
digitalWrite(A_REN, HIGH);
digitalWrite(A_LEN, HIGH);
digitalWrite(B_REN, HIGH);
digitalWrite(B_LEN, HIGH);
pararMotores();
}
void loop() {
if (SerialBT.available()) {
comando = SerialBT.read();
}
switch (comando) {
case 'F': // Frente
22
frenteMotores();
break;
case 'B': // Trás
trasMotores();
break;
case 'L': // Esquerda
virarEsquerda();
break;
case 'R': // Direita
virarDireita();
break;
case 'l': // Esquerda trás
virarEsquerdaTras();
break;
case 'd': // Direita trás
virarDireitaTras();
break;
case 'w': // Comemoração
23
comemorar();
break;
case 'S': // Soltou o botão → PARA TUDO
default:
pararMotores();
break;
}
}
void frenteMotores() {
// A para frente
digitalWrite(A_RPWM, HIGH);
digitalWrite(A_LPWM, LOW);
// B para frente
digitalWrite(B_RPWM, HIGH);
digitalWrite(B_LPWM, LOW);
}
void trasMotores() {
// A trás
digitalWrite(A_RPWM, LOW);
digitalWrite(A_LPWM, HIGH);
24
// B trás
digitalWrite(B_RPWM, LOW);
digitalWrite(B_LPWM, HIGH);
}
void virarEsquerda() {
// A frente (direito roda)
digitalWrite(A_RPWM, HIGH);
digitalWrite(A_LPWM, LOW);
// B parado
digitalWrite(B_RPWM, LOW);
digitalWrite(B_LPWM, LOW);
}
void virarDireita() {
// B frente (esquerdo roda)
digitalWrite(B_RPWM, HIGH);
digitalWrite(B_LPWM, LOW);
// A parado
digitalWrite(A_RPWM, LOW);
digitalWrite(A_LPWM, LOW);
25
}
void virarEsquerdaTras() {
// B tras
digitalWrite(B_RPWM, LOW);
digitalWrite(B_LPWM, LOW);
// A parado
digitalWrite(A_RPWM, LOW);
digitalWrite(A_LPWM, HIGH);
}
void virarDireitaTras() {
// B parado
digitalWrite(B_RPWM, LOW);
digitalWrite(B_LPWM, HIGH);
// A tras
digitalWrite(A_RPWM, LOW);
digitalWrite(A_LPWM, LOW);
}
void comemorar() {
// B tras
26
digitalWrite(B_RPWM, LOW);
digitalWrite(B_LPWM, HIGH);
// A frente
digitalWrite(A_RPWM, HIGH);
digitalWrite(A_LPWM, LOW);
}
void pararMotores() {
digitalWrite(A_RPWM, LOW);
digitalWrite(A_LPWM, LOW);
digitalWrite(B_RPWM, LOW);
digitalWrite(B_LPWM, LOW);
}
