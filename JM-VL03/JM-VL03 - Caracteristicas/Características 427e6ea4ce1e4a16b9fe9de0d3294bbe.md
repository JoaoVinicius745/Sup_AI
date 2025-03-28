# Características

# Características gerais do produto VL-03

---

O JM-VL03 é um rastreador GPS 4G LTE projetado principalmente para o gerenciamento de veículos.

A capacidade de trabalhar em tensão de entrada de 9-90V permite sua compatibilidade com uma ampla gama de veículos.

Uma antena GPS avançada oferece uma forte aquisição de sinal e capacidade de posicionamento mais preciso.

Projetado com um sistema de análise de comportamento de condução e vários alertas, o JM-VL03 pode aumentar a segurança de condução e a segurança do veículo de forma mais eficaz.

- 4G LTE CAT1 c/ fallback 2G GSM
- Tensão nominal de 9 a 90V
- Analise de comportamento de condução
- Botão SOS
- Múltiplos alertas
- Corte de alimentação/combustível
- Status de violação
- **Certificado de Homologação: 15220-22-11209**

## Alimentação

---

| Faixa de alimentação | Bateria interna |
| --- | --- |
| 9 - 90 VDC | 3.7V/60 mAh |

## Entradas e saídas

---

2 entradas digitais, sendo:

- Ignição (ACC)
- Botão de pânico (SOS)

1 saídas digital, sendo:

- Relé

## Rede celular

---

| **Comunicação de rede** | **LTE** | **GSM** |
| --- | --- | --- |
| Frequência | B1, B3, B7, B8, B28 | 850/950/1800/1900 MHz |

SIM CARD: Micro SIM

## GNSS

---

| Sistema de posicionamento | GPS+LSB+BDS |
| --- | --- |
| Frequência | L1 |
| Precisão de posicionamento | <2,5m CEP |
| Sensibilidade de pista | -165 dBm |
| Sensibilidade de aquisição | -148 dBm |

## Temperatura de operação e proteção

**Temperatura operacional:** -20°C a +70°C

**Índice de proteção:**  IP65

## Características

---

| Sensores | Acelerômetro |
| --- | --- |
| Cenários | Alerta de movimento do veiculo, alerta de excesso de velocidade, cercas, detecção de bateria do veiculo, fonte de alimentação desconectada |
| Analise de condução | Aceleração, frenagem e curva brusca, detecção de colisão |

# Esquema de ligação - Cabo

---

Para ilustrar como deve ser feita a instalação elétrica do VL-03 no veículo, segue abaixo o esquemático de instalação do mesmo integrado com os periféricos:

![Design sem nome (7).png](Caracteri%CC%81sticas%20427e6ea4ce1e4a16b9fe9de0d3294bbe/Design_sem_nome_(7).png)

# LED Status

**Para bateria:**

![https://wiki.jimibrasil.com.br/bateria_sem_escala_vl03_recortado_.png](https://wiki.jimibrasil.com.br/bateria_sem_escala_vl03_recortado_.png)

**Para GPS:**

![https://wiki.jimibrasil.com.br/gps_sem_escala_vl03.png](https://wiki.jimibrasil.com.br/gps_sem_escala_vl03.png)

**Para rede celular:**

![https://wiki.jimibrasil.com.br/network_sem_escala_vl03.png](https://wiki.jimibrasil.com.br/network_sem_escala_vl03.png)

## Suspensão de leds

---

**LEDSW,A#**

Onde:

**LEDSW:** Descreve o comando a ser enviado

**A** = ON/OFF, **padrão: OFF**

- **ON** significa que os LEDs estão sempre acesos;
- **OFF** significa que os LEDs irão dormir automaticamente enquanto nada de anormal ocorrer.

Exemplo: **LEDSW,ON#**

### **Consulta**

**Para consulta, enviar:** **LEDSW#**