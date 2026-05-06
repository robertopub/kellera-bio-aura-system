# Dia 3 - Primeiro sensor funcionando no ESP32

## Objetivo
Fazer a primeira leitura de temperatura em tempo real usando ESP32 + sensor DS18B20.

---

## Componentes utilizados

- ESP32
- Sensor DS18B20
- Protoboard
- Jumpers
- Arduino IDE

---

## Ligações realizadas

### Sensor DS18B20

| Sensor | ESP32 |
|---|---|
| VCC (+) | 3V3 |
| GND (-) | GND |
| OUT | D4 |

---

## Bibliotecas instaladas

- OneWire
- DallasTemperature

---

## Código utilizado

```cpp
#include <OneWire.h>
#include <DallasTemperature.h>

#define ONE_WIRE_BUS 4

OneWire oneWire(ONE_WIRE_BUS);

DallasTemperature sensors(&oneWire);

void setup() {
  Serial.begin(115200);

  sensors.begin();

  Serial.println("Sensor DS18B20 iniciado!");
}

void loop() {

  sensors.requestTemperatures();

  float temperatura = sensors.getTempCByIndex(0);

  Serial.print("Temperatura: ");
  Serial.print(temperatura);
  Serial.println(" °C");

  delay(2000);
}

---

## Resultado

Leitura de temperatura funcionando em tempo real no Serial Monitor.

O sensor respondeu corretamente ao toque da mão, alterando os valores de temperatura.

---

## Aprendizados

- Configuração do ESP32
- Comunicação serial
- Uso do Arduino IDE
- Instalação de bibliotecas
- Leitura digital de sensores
- Integração hardware + software

---

## Próximo passo

Adicionar LED RGB para criar resposta visual baseada na temperatura.

---

Kellera:
Tecnologia para ampliar capacidades humanas.
