# 🧠 A.T.E.N.A. — Gêmeo digital cognitivo para equipamentos industriais

## 🎯 Objetivo
Projeto de TCC: um aplicativo desktop que dá "voz" a um equipamento industrial,
combinando:
- Assistente de voz e chat com IA (Gemini), respondendo ao nome **"ATENA"**
- Telemetria em tempo real via **MQTT**
- Viewer 3D do equipamento
- Ações reais no equipamento, **só com confirmação explícita do operador**
- Alertas proativos quando um sensor sai da faixa configurada

O equipamento usado como referência é um cilindro pneumático com sensores M12, mas a
aplicação é configurável por projeto — serve qualquer equipamento com sensores/
atuadores MQTT.

---

## 🛠 Tecnologias
- Python / CustomTkinter
- Google Gemini (function calling)
- paho-mqtt
- PyVista / VTK (viewer 3D)
- edge-tts + reconhecimento de voz (wake word)

---

## 📌 Status
Em desenvolvimento ativo. O código-fonte é um projeto pessoal/TCC e por isso não é
público — mas o progresso é documentado publicamente:

➡️ **[github.com/andrecossa-eng/atena-updates](https://github.com/andrecossa-eng/atena-updates)**
(changelog, decisões de design e capturas de tela conforme o projeto avança)
