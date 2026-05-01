# Dia 2 - Primeira execução com ESP32

Hoje foi o primeiro contato real com hardware do projeto Kellera Bio Aura System.

## O que foi feito

- Instalação da Arduino IDE
- Configuração do suporte para ESP32
- Identificação do chip USB (CH9102X)
- Instalação do driver correto
- Reconhecimento da porta COM no sistema (COM3)
- Upload do primeiro código para o ESP32

## Desafios enfrentados

Durante o processo, ocorreram alguns erros importantes:

- Porta serial não aparecia
- Erro de conexão com ESP32
- Problema de modo de boot (download mode)

Todos foram resolvidos com:
- Instalação do driver correto (CH9102X)
- Seleção da porta COM correta
- Uso do botão BOOT para upload manual

## Primeiro código executado

```cpp
void setup() {
  Serial.begin(115200);
}

void loop() {
  Serial.println("ESP32 funcionando!");
  delay(1000);
}