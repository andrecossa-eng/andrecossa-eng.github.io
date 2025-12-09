# 🛠️ Simulações CNC & Análises Estruturais (Projeto Suporte de Celular em formato de Dinossauro)

<img width="1364" height="723" alt="image" src="https://github.com/user-attachments/assets/449eb2a2-c387-4f75-9a46-2d28c917f17a" />
<img width="1366" height="726" alt="image" src="https://github.com/user-attachments/assets/10c97a09-faff-470d-8974-61b595d8c5b4" />
<img width="491" height="363" alt="image" src="https://github.com/user-attachments/assets/3a5e71ce-77c0-44ff-8742-032f1a112cfb" />
<img width="519" height="367" alt="image" src="https://github.com/user-attachments/assets/88d892db-efb4-459e-9029-796c5d576916" />
<img width="509" height="298" alt="image" src="https://github.com/user-attachments/assets/20d8cfe0-23d6-494a-bb0e-6ffa1652727c" />
<img width="309" height="344" alt="image" src="https://github.com/user-attachments/assets/9c11a4d9-4a02-42ad-b07e-2e4dfd903d43" />

## 🎯 Objetivo  
Simulações estruturais e geométricas envolvendo:  
- Equilíbrio de peças  
- Usinagem CNC  
- Tensões, flexões, apoios  
- Otimização de suportes  

---

## 🛠 Tecnologias  
- Esticam 
- AutoCAD
- Análise estática  
- Nylon
- Inventor
- FEA  

## 📐 Desenhos técnicos

<img width="625" height="441" alt="image" src="https://github.com/user-attachments/assets/5ffc9a99-1829-487e-b8e3-aa0f608aa5f8" />
<img width="626" height="440" alt="image" src="https://github.com/user-attachments/assets/ec751687-660d-4728-8dee-8891e707f613" />
<img width="625" height="441" alt="image" src="https://github.com/user-attachments/assets/937aec63-9ab1-4533-adb4-5ea0bab40596" />

---

## 💻 Códigos NC

Código Cabeça:
N05 G90
N10 M03 S2400
N15 G00 Z5.0000
N20 G00 X-0.4313 Y-1.6553
N25 G00 Z0.5000
N30 G01 Z0.0000 F300 S2400
N35 G01 Z-3.0000
N40 G03 X5.9286 Y-4.0000 I6.4400 J7.6707 F200
N45 G01 X31.0462
N50 G03 X30.7737 Y35.9936 I-0.0446 J19.9974
N55 G03 X27.0000 Y32.0000 I0.2263 J-3.9936
N60 G01 Y24.0000
N65 G03 X31.1425 Y19.9924 I4.0177 J0.0082
N70 G02 X30.9286 Y16.0000 I-0.1446 J-1.9942
N75 G01 X5.9286
N80 G03 X-0.4313 Y-1.6553 I0.0731 J-9.9995
N85 G00 Z5.0000
N90 G00 X0.0000 Y0.0000
N95 M05
N100 M30

Código da base:
N05 G90
N10 M03 S2400
N15 G00 Z5.0000
N20 G00 X-4.0000 Y0.0000
N25 G00 Z0.5000
N30 G01 Z0.0000 F300 S2400
N35 G01 Z-3.0000
N40 G03 X0.0000 Y-4.0000 I4.0000 J0.0000 F200
N45 G01 X34.0000
N50 G03 X38.0000 Y0.0000 I0.0000 J4.0000
N55 G01 Y8.9288
N60 G02 X42.0000 I2.0000 J0.0677
N65 G01 Y0.0000
N70 G03 X46.0000 Y-4.0000 I4.0000 J0.0000
N75 G01 X80.0000
N80 G03 X84.0000 Y0.0000 I0.0000 J4.0000
N85 G01 Y30.0002
N90 G03 X75.9924 Y29.8577 I-4.0050 J-0.0053
N95 G02 X72.0000 Y30.0716 I-1.9942 J0.1446
N100 G01 Y41.4248
N105 G03 X70.1974 Y44.7672 I-4.0000 J0.0000
N110 G03 X22.4738 Y51.0681 I-30.1829 J-44.7259
N115 G03 X20.0002 Y47.3708 I1.5265 J-3.6973
N120 G01 Y33.0714
N125 G02 X14.0002 I-3.0000 J-0.0681
N130 G01 Y40.0000
N135 G03 X7.5626 Y43.1714 I-4.0000 J0.0000
N140 G03 X-3.3600 Y32.1700 I32.0720 J-42.7650
N145 G03 X-3.9998 Y30.0000 I3.3602 J-2.1700
N150 G01 X-4.0000 Y0.0000
N155 G00 Z5.0000
N160 G00 X0.0000
N165 M05
N170 M30

## 📘 Resultados  
- Peças com estabilidade verificada  
- Redução de falhas  
- Usinagem otimizada antes da CNC  
