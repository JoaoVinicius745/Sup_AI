# Porta serial TTL

# **Introdução**

---

## **Descrição do cabo de comunicação TTL**

| TTL | Vermelho | 5V/500 mAh |
| --- | --- | --- |
|  | Azul | RX |
|  | Verde | TX |
|  | Preto | GND |

**Obs:** Se usar acessórios, não ligue a alimentação no cabo de energia do TLL (cabo vermelho). Use uma conexão separada, mas lembre-se: a fonte de energia deve ser a mesma para o equipamento e o acessório.

## Habilitação Serial

---

Para utilização da comunicação serial, é utilizado o seguinte comando:

**TRAN,SW,A,B#**

Onde:

**TRAN:** Descreve o comando a ser enviado

**SW:** Liga/desliga monitoramento da porta TTL (ON/OFF);

**A:** Ativação da porta serial TTL

- A=3: Dados Transparentes

**B:** Baud Rate (0-6)

- 0: 4800bps;
- 1: 9600bps;
- 2: 19200bps;
- 3: 14400bps;
- 4: 38400bps;
- 5: 57600bps;
- 6: 115200bps;

Exemplo: **TRAN,ON,3,2#**

### Consulta

**Para consulta, enviar:** **TRAN#**

Para comunicação via SSCOM, o BAUDRATE deve estar configurado **sempre** para 115200, caso a porta serial esteja ATIVADA, desenergize completamente o equipamento removendo POS, NEG, ACC e o Switch da Bateria deve estar chaveado para o OFF e ligue o equipamento novamente,  ao inicia o equipamento você verá na tela do SSCOM a informação de **DS18B20 Temp Init!** após isso você pode mandar **TRAN,OFF** caso deseje desabilitar a porta serial para voltar a realizar configuração via serial