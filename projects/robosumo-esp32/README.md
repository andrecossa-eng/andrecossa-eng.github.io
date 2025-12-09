# 🤖 Robô Sumô – ESP32 + BTS7960

![Robot Sumo](https://upload.wikimedia.org/wikipedia/commons/3/3d/Robot_sumo.jpg)

## 🎯 Objetivo  
Construir um robô sumô com:  
- Controle via Bluetooth  
- Dois drivers BTS7960  
- Motores de vidro elétrico  
- Estratégia de combate  
- Leitura de sensores ultra-sônicos  

---

## 🛠 Tecnologias  
- ESP32  
- Bluetooth Serial  
- BTS7960  
- Motores DC  
- Sensores HC-SR04  
- PWM  

---

## ⚙ Arquitetura
[ESP32] → [BTS7960] → [Motores]
↓
[Bluetooth App]

---

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
]

💥 Resultados

Robô rápido, forte e responsivo

Comunicação Bluetooth fluida

Estrutura para competições
