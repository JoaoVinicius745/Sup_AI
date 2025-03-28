# Características

# Características gerais do produto VL-02

---

O JM-VL02 foi projetado para lidar com aplicações de frotas industriais e comerciais, desde agências de aluguel e transporte público até equipamentos de construção e muito mais.

E, usando comunicações LTE (Cat M1/NB-IoT) e GSM de ponta, o VL02 ajudará você a maximizar as operações de sua frota nos próximos anos.

- 4G LTE CAT-M1/NB2 e GSM
- Detecção de ignição
- Botão SOS
- Múltiplos alertas
- Corte de alimentação/combustível
- Status de abertura e fechamento de portas
- Leitura de combustível/temperatura (opcional)
- Leitura RFID (opcional)
- **Certificado de Homologação: 19088-22-11209**

## Alimentação

---

| Faixa de alimentação | Bateria interna |
| --- | --- |
| 9 - 36 VDC | 3.7V/300 mAh |

## Entradas e saídas

---

3 entradas digitais, sendo:

- Ignição (ACC)
- Botão de pânico (SOS)
- Entrada auxiliar

2 saídas digital, sendo:

- Relé
- Saída auxiliar

## Rede celular

---

| **Comunicação de rede** | **LTE** | **GSM** |
| --- | --- | --- |
| Frequência | B1, B3, B7, B8, B28 | 850/950/1800/1900 MHz |

SIM CARD: Cartão padrão

## GNSS

---

| Sistema de posicionamento | GPS+LSB |
| --- | --- |
| Frequência | L1 |
| Precisão de posicionamento | <2,5m CEP |
| Sensibilidade de pista | -165 dBm |
| Sensibilidade de aquisição | -148 dBm |

## Temperatura de operação e proteção

---

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

Para ilustrar como deve ser feita a instalação elétrica do VL-02 no veículo, segue abaixo o esquemático de instalação do mesmo integrado com os periféricos:

![https://wiki.jimibrasil.com.br/esquema_eletrico_cabo_vl-02_v2.0.jpg](https://wiki.jimibrasil.com.br/esquema_eletrico_cabo_vl-02_v2.0.jpg)

# Leds de status

---

**Para bateria:**

![https://wiki.jimibrasil.com.br/bateria_sem_escala.png](https://wiki.jimibrasil.com.br/bateria_sem_escala.png)

**Para GPS:**

![https://wiki.jimibrasil.com.br/gps_sem_escala.png](https://wiki.jimibrasil.com.br/gps_sem_escala.png)

**Para rede celular:**

![https://wiki.jimibrasil.com.br/network_sem_escala.png](https://wiki.jimibrasil.com.br/network_sem_escala.png)

## Suspensão de led

---

**LEDSLEEP,A#**

Onde:

**LEDSLEEP**: Descreve o comando a ser enviado;

**A**: Habilita/desabilita o modo de suspensão de led: **ON/OFF**

- **ON:** Quando o dispositivo está carregando, a luz apaga após 5 minutos; Quando o GPS está funcionando, a vibração não pode despertar a luz; quando o gps está desligado, o choque pode despertar a luz.
- **OFF:** Todas as luzes estão sempre acesas, **padrão: ON**

Exemplo: **LEDSLEEP,ON#**

### **Consulta**

**Para consulta, enviar: LEDSLEEP#**