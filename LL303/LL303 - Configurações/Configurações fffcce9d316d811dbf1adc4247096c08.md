# Configurações

# Configurações iniciais

---

## Definição de APN

---

Obtenha as informações de APN da operadora do cartão SIM. Em seguida, envie o comando SMS para o número do cartão SIM do dispositivo para definir o parâmetro APN. O dispositivo responderá "OK" se o APN for configurado com sucesso.

Comando SMS**: APN, apnname#**

Por exemplo:

- **APN,internet#** ("internet" é a operadora do APN)

Algumas operadores podem ter nome de usuário e senha.

Comando SMS: **APN,apnname,usuário,senha#**

Por exemplo:

- **APN,internet,cliente,AMENA#**

## Definição do servidor

---

Comando SMS: **SERVER,mode,domainName/IP,port#**

Por exemplo:
• **SERVER,1,gtws.jimibrasil.com.br,21001#**

                              ou
• **SERVER,0,3.131.107.97,21001#**

Mode = 1, significa definido com nome de domínio.

Mode = 0, significa definido com endereço IP.

## Definição do MODE

---

Para definição de posicionamento por parte do dispositivo, é necessária a realização utilizando os seguintes parâmetros: MODE, seriam 3 modos de trabalho:

<aside>

***N = 1:** Modo de posicionamento temporizado*

T = Intervalo de localização

- 0 (Desativar upload automático)
- 10 ~ 86.400 segundos
- Não há valor padrão
- Este parâmetro deve ser definido

A = interruptor GPS

- 0 = GPS desligado
- 1 = GPS ligado
- **Padrão:** A = 1

B = interruptor Wi-Fi

- 0 = WIFI desligado
- 1 = WIFI ligado
- **Padrão:** B = 1

C = interruptor LBS

0 = LBS desligado 

1 = LBS ligado

**Padrão:** C = 1

D = BLE

0 = BLE desligado 

1 = BLE ligado

Padrão: D = 0

Comandos SMS: **MODE,N,T,A,B,C,D#**

</aside>

<aside>

***N = 2**: Modo de posicionamento inteligente*

T1 = Intervalo de upload de dados de localização em estado móvel

- 10 - 86400s
- **Padrão:** T=20s

T2 = Intervalo de upload de dados de localização em estado estático

- 0 (Sem upload, em repouso)
- 180 -86400s
- Disponível quando GPSDUP está habilitado
- **Padrão:** 0s

A = Interruptor GPS

- 0 = GPS desligado
- 1 = GPS ligado

B = Interruptor Wi-Fi

- 0 = WIFI desligado
- 1 = WIFI ligado
- **Padrão:** B = 1

**C** = interruptor LBS

0 = LBS desligado

1 = LBS ligado

**Padrão:** C = 1

D = BLE

0 = BLE desligado 

1 = BLE ligado

**Padrão:** D = 0

E = GPRS

0 = GPRS desligado quando inativo

1 = GPRS sempre ligado

**Padrão:** E = 1

Comandos SMS: **MODE,N,T1,T2,A,B,C,D,E#**

</aside>

<aside>

***N = 3**: Modo de economia de bateria*

T1 = Hora de início

- Formato: HH:MM

T2 = Intervalo de tempo

- 5 a 43.200 minutos
- Não há valor padrão

A = GPS

0 = GPS desligado 

1 = GPS ligado 

**Padrão:** A=1

B = Wi-Fi

0 = WIFI desligado 

1 = WIFI ligado

**Padrão:** B = 1

**C** = LB

0 = LBS desligado 

1 = LBS ligado

**Padrão:** C = 1

D = BLE

0 = BLE desligado 

1 = BLE ligado

Padrão: D = 0

Comandos SMS: **MODE,N,T1,T2,A,B,C,D#**

</aside>

**MODE#**

⇒ Consulte a configuração atual do modo de trabalho

# Comandos

---

## Upload de dados GPS

---

**GPSDUP,A#**

A = ON/OFF (Apenas o modo 1 é válido)

ON = O ponto de ancoragem GPS é carregado no terminal no intervalo definido

OFF = Fecha esta função (Desempenha apenas uma função auxiliar, sendo recomendado desligar para economizar energia)

⇒ Consulte a configuração atual do modo de trabalho.

**GPSDUP#**

## Configuração de duração do som da buzzer

---

**SPEAK,X,T#**

Configuração de duração do som da buzzer

X = ON/OFF = O buzzer soará quando o alarme de remoção for acionado

T = Duração do som da buzzer após acionamento do alarme de remoção, faixa de ajuste: 1-300s; Padrão, 60 seg

⇒ Consulte a configuração atual do modo de trabalho

**SPEAK#**

## Habilitar/desabilitar GPRS

---

**GPRS,X#**

X = ON/OFF

ON = Ativa o GPRS

OFF = Desabilita o GPRS

Padrão: ON

⇒ Consulte a configuração atual do modo de trabalho

**GPRS#**

## Alarme de vibração

---

**SENALM,A,M#**

A = ON/OFF,

**Padrão:** OFF

M = 0/1 (Forma de alarme)

0: Somente GPRS

1: SMS+GPRS

**Padrão:** 1

⇒ Consulte a configuração atual do modo de trabalho

**SENALM#**

---

**LEVEL,A#**

A = 1 - 5 (Faixa de sensibilidade) 1 é mais sensível

**Padrão:** 3

⇒ Consulte a configuração atual do modo de trabalho

**LEVEL#**

## Alerta de bloqueio de GPRS

---

**GPRSALM,ON#**

Envia alarme quando o servidor não responde

Forma de alarme: SMS

**GPRSALM,OFF#**

Fechar o alarme de bloqueio GPRS

⇒ Consulte a configuração atual do modo de trabalho

**GPRSALM#**

## **AUTOSLEEP**

---

**AUTOSLEEP,A,B,C,D#**

**A** = ON/OFF

**Padrão:** OFF

**B** = Porcentagem de energia usada para mudar o modo de operação de alto para baixo

Faixa de configuração: 10 - 90%

**Padrão:** 20

C = Porcentagem de energia usada para mudar o modo de operação de baixo para alto

Faixa de configuração: 20 - 100％

**Padrão:** 30

D = Intervalo de posicionamento para mudar para o modo 3

5 ~ 43200 minutos

**Padrão:** 1440

⇒ Consulte a configuração atual do modo de trabalho

**AUTOSLEEP#**

## **Alarme anti-remoção (Tampa)**

---

**REMALM,A,M#**

**A** = ON/OFF

**Padrão:** ON

**M** = 0/3 (Modo de alarme)

M = 0: Somente GPRS

M = 1: SMS+GPRS

**Padrão:** 0

**REMALM,OFF#**

Desligue o alarme de violação e o alarme de desligamento

⇒ Consulte a configuração atual do modo de trabalho

**REMALM#**

## Envio de status para o servidor

---

**SCS,A,B#**

A = **ON/OFF**

**Padrão: OFF**

B = Intervalo de atualização de status 

1 ~ 3600 segundos

**Padrão: 5**

⇒ Consulte a configuração atual do modo de trabalho

**SCS#**

## **BMT**

---

**BMT#**

Verifique o método de carregamento da bateria, a tensão da bateria, a temperatura da bateria, a corrente de carga e a tensão de carga

## **Leitor RFID**

---

**RFID,A#**

**A** = **ON/OFF**

**Padrão:** OFF

⇒ Consulte a configuração atual do modo de trabalho

**RFID#**

## **Sensor Bluetooth**

---

**BTMAC,ADD,MAC0,MAC1,MAC2,…,MAC9#**

MAC0 = MAC do primeiro sensor Bluetooth

MAC1 = MAC do segundo sensor Bluetooth

MAC2 = MAC do terceiro sensor Bluetooth

…

MAC9 = MAC do décimo sensor Bluetooth

**Por exemplo:** **BTMAC,ADD,B4:A8:28:37:05:E5,,,,,,,,,#**

Exclua todos os sensores Bluetooth MAC:

**BTMAC,DELALL#**

## **Cancel**

---

**CANCEL#**

Quando o dispositivo acionou o evento de violação e entrou no modo de rastreamento, este comando cancelará o modelo de rastreamento e recuperará o modo de trabalho original.

## Consultar o MAC atual

---

**BTMAC#**

## Verificar o status do trabalho e os principais parâmetros

---

**CHECK#**

## **Reset**

---

**RESET#**

O equipamento vai reiniciar em 20 segundos ao receber esse comando

## Versão do Firmware

---

**VERSION#**

Consulte a configuração do *Firmware*

## Formatar

---

**FACTORY#**

Recupere todas as configurações de fábrica (Exceto servidor e APN)

## Consultar o servidor e configurações de APN

---

**GPRSSET#**

## **Status**

---

**STATUS#**

Solicite o status do equipamento

## Verificar a URL

---

**WHERE#**

## Verifique a posição do equipamento

---

**POSITION#**

## Fuso horário

---

**GMT,A,B,C#**

**A** = E ou W

"E" significa fuso horário oriental

"W" significa fuso horário ocidental

**Padrão:** E

**B** = 0~12

**Padrão de fuso horário:** 8

**C** = 0/15/30/45

Meio horário

**Padrão:** 0

Verifique os parâmetros do fuso horário atual:

**GMT#**

## Tempo de GPS por vibração

---

Após "x" tempo sem nenhuma vibração, o equipamento entrará no modo de economia. Para configurar a função, utiliza-se o comado: 

**SENDS,A#**

Onde:

**SENDS:** Descreve o comando a ser enviado;

**A:** 0 a 300 minutos, tempo de detecção de vibração;

Exemplo: **SENDS,5#**

⇒ Consulte a configuração atual do modo de trabalho

**SENDS#**