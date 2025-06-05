# Projeto de Automação Residencial com Raspberry Pi Pico W e MQTT

Este projeto demonstra um sistema básico de automação residencial utilizando a placa Raspberry Pi Pico W. Ele permite o controle de dispositivos e o monitoramento de sensores através do protocolo MQTT, com comunicação via Wi-Fi.

## Base e Inspiração

Este trabalho é uma adaptação e evolução de um projeto anterior denominado **"WS_IoT"**. A sua concepção e desenvolvimento foram fortemente baseados no projeto desenvolvido pelo **Professor Ricardo Prates**.

## Visão Geral

O sistema atual permite:

* Controlar a cor de diferentes seções de uma fita de LEDs WS2812 (simulando ambientes como Quarto, Sala e Exterior) através de comandos MQTT.
* Acionar um buzzer de forma via MQTT.
* Monitorar a temperatura interna do microcontrolador RP2040, com os dados publicados via MQTT.
* Utilizar um botão físico para reiniciar o Pico em modo BOOTSEL para fácil reprogramação.

## Tecnologias

* Linguagem C/C++ com o SDK do Raspberry Pi Pico
* Protocolo MQTT para comunicação IoT
* Pilha de rede LwIP para conectividade TCP/IP
* Wi-Fi (integrado ao Pico W)
* PIO (Programmable I/O) para controle dos LEDs WS2812
* PWM para controle do buzzer
* ADC para leitura do sensor de temperatura interno

## Configuração

1.  **Credenciais:** As credenciais da sua rede Wi-Fi e do servidor/broker MQTT (endereço, porta, usuário, senha) devem ser configuradas diretamente nos `#define` presentes no arquivo principal do código-fonte (ex: `main.c`).
2.  **Broker MQTT:** Este projeto foi testado utilizando um celular Android como broker MQTT, com o Pico W atuando como cliente.
3.  **Tópicos MQTT:** Os tópicos para controle de cor dos LEDs (ex: `/casa/quarto/cor`), acionamento do buzzer (`/casa/cortina/comando`), e outros, estão definidos no código.

## Vídeo Demonstrativo

Assista a uma demonstração do projeto em funcionamento:

**https://youtu.be/qb3NYBdKgMk**

---
