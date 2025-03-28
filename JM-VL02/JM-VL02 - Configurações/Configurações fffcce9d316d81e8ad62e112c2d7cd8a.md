# Configurações

# Configurações iniciais

Neste topico será descrito uma configuração basica para um bom funcionamento do equipamento. Os comandos listados abaixo podem ser enviados ao equipamento tanto em  GPRS e SMS, para todos os métodos de envio o comando permanece o mesmo.

### **1 – APN**

---

**1.1** – Para configuração de APN,  é utilizado o comando:

**APN,apnname#**

Ou caso seja uma APN privada

**APN,apnname,user,pwd#**

Onde:

**APN: D**escreve o comando a ser enviado;

**apnname:** nome de usuário da rede;

**user:** Usuário;

**pwd:** Senha;

Exemplo: **APN,teste.teste.com.br#** ou **APN,teste.teste.com.br,teste,teste#**

**Para consulta, enviar: APN#**

- Pode ser enviado por: **#SMS #SERVIDOR**

**1.2** – Para utilização de configuração automática de APN é utilizado o comando

**ATENÇÃO**: **Se estiver utilizando APN privada desative a APN automática!**

**ASETAPN,SW#**

Onde:

**ASETAPN:** Descreve o comando a ser enviado;

**SW:** Habilita/desabilita

ON: Habilita

OFF: Desabilita

Exemplo: **ASETAPN,OFF#**

**Para consulta, enviar:** ASETAPN#

- Pode ser enviado por: **#SMS #SERVIDOR**

### **2 – Servidor**

---

 **2.1** – O comando utilizado para definição de endereço e porta do servidor é o:

**SERVER,mode,domainName/IP,port,protocol**#

Onde:

**SERVER:** Descreve o comando a ser enviado;

**Mode:** Definição entre domínio ou IP

0: IP

1: Nome do domínio (DNS)

**domainName/IP:** IP ou DNS;

**port:** Porta do servidor

**protocol:** Definição do tipo de protocolo

0: TCP

1: UDP

Exemplo: **SERVER,1,gpsdev.tracksolid.com,21100,0#**

**Para consulta, enviar:** SERVER#

• Pode ser enviado por: **#SMS #SERVIDOR**

### **3 – GPS**

---

**3.1** – Para envio de dados com informações GPS, utilize o comando:

**GPSDUP,ON#**

****Exemplo: **GPSDUP,ON#**

**Para consulta, enviar: GPSDUP#**

- Pode ser enviado por: **#SMS #SERVIDOR**

### **4 - Efeito estrela**

---

**4.1** – Para que o terminal desligue o filtro de efeito estrela, envie o seguinte comando:

**SF,OFF#**

****Exemplo: **SF,OFF#**

**Para consulta, enviar:** **SF#**

- Pode ser enviado por: **#SMS #SERVIDOR**

### 5 - Tempo de posição

---

**5.1** – Possibilitando ser configurado o intervalo de tempo para envio de posições GPS, tanto em ignição ligada quanto em ignição desligada.

**ATENÇÃO: Quando habilitado o envio por tempo, o envio de posições por distância é definido automaticamente com o valor 0.**

Para configurar, utiliza-se o seguinte comando:

**TIMER,T1,T2#**

Onde:

**TIMER:** Descreve o comando a ser enviado;

**T1:** Intervalo de transmissão com ignição ligada (0, ou, de 5 a 18000 segundos);

**T2:** Intervalo de transmissão com ignição desligada (0, ou, de 5 a 18000 segundos);

Exemplo: **TIMER,20,60#**

**Para consulta, enviar: TIMER#**

- Pode ser enviado por: **#SMS #SERVIDOR**

### **6 – Odômetro**

---

**6.1** – Para inserção de valores de odometro, o comando para sua configuração é:

**MILEAGE,A,B#**

Onde:

**MILEAGE:** Descreve o comando a ser enviado;

**A:** Ativa/desativa contagem de odometro, **Padrão: OFF**

**B:** Valor inicial de odometro, (0 a 999999 km), **Padrão: 0**

Exemplo: **MILEAGE,ON,1000#**

**Para consulta, enviar:** **MILEAGE#**

- Pode ser enviado por: **#SMS #SERVIDOR**

# Consultas

---

## Versão de firmware

---

**Para consulta, enviar:** VERSION#

**A resposta será:**  [VERSION]NT06L_GT06L_WAAG_V7.0_210112.0927

## Status de comunicação

---

**Para consulta, enviar:** STATUS#

**A resposta será:**

Battery:4.20V,NORMAL; SERVER:Link Up, network:"GSM",(4); GPS:Successful positioning; SVS Used in fix:3(9); , GPS Signal Level:38,26,33 ACC:ON; Defense:OFF;

Onde:

Battery:4.20V: Bateria interna

SERVER:Link Up: Comunicação com o servidor

network:"GSM": Conexão de rede

GPS: Successful positioning: Conexão de GPS

SVS Used in fix:3(9): Quantidade de GPS

GPS Signal Level: 38,26,33: Sinal GPS

ACC: ON: Ignição

Defense: OFF: Defesa

## Rede

---

**Para consulta, enviar:** **GPRSSET#**

**A resposta será:**

GPRS: ON; Currently use APN:allcom.vivo.com.br,allcom,allcom; Server:1,gpsdev.tracksolid.com,21100,0; URL:http://maps.google.com/maps?q=;

**Onde:**

GPRS: ON: Conexão de rede

Currently use APN: allcom.vivo.com.br,allcom,allcom: Configuração de APN

Server: 1,gpsdev.tracksolid.com,21100,0: Configuração de servidor

URL: http://maps.google.com/maps?q=: Mapa de coordenadas

## Coordenadas GPS

---

**Para consulta, enviar:** **WHERE#**

**A resposta será:**

Current position! Lat:S23.525024,Lon:W46.679787,Course:263.28,Speed:0.00Km/h,DateTime:2021-10-29 11:11:43

Onde:

Current position! Lat:S23.525024,Lon:W46.679787: Coordenadas GPS

Course: 263.28: Curso GPS

Speed: 0.00 Km/h: Velocidade

DateTime:2021-10-29 11:11:43: Data e hora

## URL

---

**Para consulta, enviar:** **URL#**

**A resposta será:**

<10-29 11:13>http://maps.google.com/maps?q=S23.524992,W46.679947

Onde:

<10-29 11:13>: Data e hora de consulta

http://maps.google.com/maps?q=S23.524992,W46.679947: Coordenadas

# Configurações

---

Nesse tópico serão descritos os comandos disponíveis no terminal, na qual podem ser enviados tanto em  GPRS, SMS e via serial, para todos os métodos de envio o comando permanece o mesmo.

**ATENÇÃO! Antes de realizar as configurações descritas nessa página, pedimos para que as configurações iniciais sejam realizadas clicando [aqui](https://www.notion.so/Configura-es-fffcce9d316d81e8ad62e112c2d7cd8a?pvs=21).**

Para envio de comados via serial: **AT^GT_CM=COMANDO,PARAMETRO#**

Para envio de comandos via SMS: **COMANDO,PARAMETRO#**

Todo comando enviado deve ser finalizado com: **#**

## APN

---

Para configuração de APN, usuário e senha é utilizado o comando:

**APN,apnname#**

Ou

**APN,apnname,user,pwd#**

Onde:

**APN:** Descreve o comando a ser enviado;

**apnname:** nome de usuário da rede;

**user:** Usuário;

**pwd:** Senha;

Exemplo: **APN,teste.teste.com.br#** ou **APN,teste.teste.com.br,teste,teste#**

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### Consulta

**Para consulta, enviar:** **APN#**

## APN Automática

---

Para utilização de configuração automática de APN é utilizado o comando:

**ASETAPN,SW#**

Onde:

**ASETAPN:** Descreve o comando a ser enviado;

**SW:** Habilita/desabilita

- ON: Habilita
- OFF: Desabilita
- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### Consulta

**Para consulta, enviar:** **ASETAPN#**

## Servidor

---

O comando utilizado para definição de endereço e porta do servidor é o:

**SERVER,mode,domainName/IP,port,protocol**#

Onde:

**SERVER:** Descreve o comando a ser enviado;

**Mode:** Definição entre domínio ou IP

- 0: IP
- 1: Nome do domínio (DNS)

**domainName/IP:** IP ou DNS;

**port:** Porta do servidor

**protocol:** Definição do tipo de protocolo

- 0: TCP
- 1: UDP

Exemplo: **SERVER,1,gpsdev.tracksolid.com,21100,0#**

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### Consulta

**Para consulta, enviar:** **SERVER#**

## Fuso horário (GMT)

---

Esse configuração permite a seleção dos fuso horário na qual os eventos gerados terão de base. Para configuração, utiliza-se o comando:

**GMT,A,B,C**#

Onde:

**GMT:** Descreve o comando a ser enviado;

**A**: Define o fuso horário a ser aplicado:

- E: fuso horário do leste;
- W: fuso horário do oeste;

**O Padrão é E: fuso horário do leste**

**B:** Padrão de fuso horário (0-12);

**C:** Meio fuso horário (0/15/30/45);

Exemplo: **GMT,W,3,0#**

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### **Consulta**

**Para consulta, enviar: GMT#**

## Fuso horário automático (GMT)

---

Há possibilidade de configuração automática do fuso horário, para isso deve-se configura-lo utilizando o seguinte comando:

**ASETGMT,SW#**

Onde:

**ASETGMT:** Descreve o comando a ser enviado

**SW:** Habilita/desabilita a configuração automática

- ON: Habilita
- OFF: Desabilita
- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### Consulta

**Para consulta, enviar:** **ASETGMT#**

## Reset (Reiniciar)

---

Para a realização de reinicialização do dispositivo, o comando utilizado é:

**RESET#**

O retorno do comando será: OK!

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

## Habilitar/desabilitar GPRS

---

É possível estabelecer o estado da rede GPRS, habilitando ou desabilitando a conexão de rede, para isso, utiliza-se o comando:

**GPRSON,X#**

Onde:

**GPRSON:** Descreve o comando a ser enviado;

**X:** Define habilitar/desabilitar

- 0: Desabilita GPRS
- 1: Habilita GPRS

Exemplo: **GPRSON,1#**

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### Consulta

**Para consulta, enviar:** **GPRSON#**

## Alarme de GPRS (Alarme)

---

Quando realizada alguma intervenção/bloqueio afim de desativar a rede GPRS, pode-se gerar um alarme para esta condição, para geração do alarme, é necessário sua configuração utilizando o seguinte comando:

**GPRSALM,S#**

Onde:

**GPRSALM:** Descreve o comando a ser enviado

**S:** Habilita/Desabilita o alarme

- ON: ligado
- OFF: desligado

Exemplo: **GPRSALM,OFF#**

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### Consulta

**Para consulta, enviar:** **GPRSALM#**

## Números para SOS

---

Para a realização de configuração de SOS, utilizam-se dois comandos, adição e delete dos números:

**Para adicionar os números SOS:**

**SOS,A,phone number 1,phone number 2,phone number 3#**

Onde:

**SOS:** Descreve o comando a ser enviado;

**Phone number 1:** Número de telefone 1;

**Phone number 2:** Número de telefone 2;

**Phone number 3:** Número de telefone 3;

Exemplo: **SOS,A,011956661773#**

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### **Consulta**

**Para consulta, enviar:  SOS#**

---

**Para deletar os números SOS:**

**SOS,D,phone number 1,phone number 2,phone number 3#**

Onde:

**SOS:** Descreve o comando a ser enviado;

**D:** Caractere fixo, descreve que é o comando de **delete;**

**Phone number 1:** Número de telefone 1;

**Phone number 2:** Número de telefone 2;

**Phone number 3:** Número de telefone 3;

Exemplo: **SOS,D,011956661773#**

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### **Consulta**

**Para consulta, enviar: SOS#**

## Central fixa para recebimento de alarmes

---

Utilizado para recebimento de alarmes gerados pelo dispositivo, o número cadastrado pode ser utilizado para controle de informações geradas, possibilitando as tratativas devidas. Para configurar, utiliza-se o seguinte comando:

**Para adicionar o número:**

**CENTER,A,phone number#**

Onde:

**CENTER:** Descreve o comando a ser enviado;

**A:** Caractere fixo, descreve que é o comando de **adição;**

**Phone number:** Número de telefone;

Exemplo: **CENTER,A,5511956661773#**

- Pode ser enviado por: **#SERVIDOR #SERIAL**

### Consulta

**Para consulta, enviar: CENTER#**

---

**Para deletar o número:**

**CENTER,D#**

Onde:

**CENTER:** Descreve o comando a ser enviado;

**D:** Caractere fixo, descreve que é o comando de **delete;**

Exemplo: **CENTER,D#**

- Pode ser enviado por: **#SERVIDOR #SERIAL**

### **Consulta**

**Para consulta, enviar: CENTER#**

## Tempo de envio de posição

---

Possibilitando ser configurado o intervalo de tempo para envio de posições GPS, tanto em ignição ligada quanto em ignição desligada. Para configurar, utiliza-se o seguinte comando:

**TIMER,T1,T2#**

Onde:

**TIMER:** Descreve o comando a ser enviado;

**T1:** Intervalo de transmissão com ignição ligada (0, ou, de 5 a 18000 segundos);

**T2:** Intervalo de transmissão com ignição desligada (0, ou, de 5 a 18000 segundos);

Exemplo: **TIMER,20,60#**

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

**OBSERVAÇÃO: Quando habilitado o envio por tempo, o envio de posições por distância é definido automaticamente com o valor 0.**

### **Consulta**

**Para consulta, enviar: TIMER#**

## Envio de posição por distância

---

Para envio de dados com informações GPS, com base na distância percorrida, utiliza-se o comando:

**DISTANCE,D#**

Onde:

**DISTANCE:** Descreve o comando a ser enviado;

**D:** Distancia (0, ou, de 50 a 10000)

Exemplo: **DISTANCE,0#**

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

**OBSERVAÇÃO: Quando habilitado o envio por distância, o envio com base no tempo é desativado.**

### **Consulta**

**Para consulta, enviar: DISTANCE#**

## Upload de dados GPS

---

Para envio de dados com informações GPS, utiliza-se o comando:

**GPSDUP,A#**

Onde:

**GPSDUP:** Descreve o comando a ser enviado;

**A:** ON/OFF, onde:

- ON: Carregar dados de localização em tempo fixo quando o GPS não estiver posicionando/suspenso ou os dados do filtro estiverem restritos.
- OFF: Não carregue dados de localização em OFF e não posicionado, estado de suspensão e estático, Padrão: OFF

Exemplo: **GPSDUP,A#**

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### **Consulta**

**Para consulta, enviar: GPSDUP#**

## Upload de dados LBS

---

Para envio de dados com informações GPS, utiliza-se o comando:

**LBSON,A,T1,T2#**

Onde:

**LBSON:** Descreve o comando a ser enviado;

**A:** ON/OFF, **Padrão: OFF**

**T1**: Intervalo de upload, (10 a 3600 segundos), **Padrão: 60 segundos**

**T2:** GPS não localiza no tempo limite (iniciar ponto de transferência LBS),(10 a 3600 segundos), **Padrão: 60 segundos**

Exemplo: **LBSON,ON,60,60#**

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### **Consulta**

**Para consulta, enviar: LBSON#**

## Tempo de envio em cerca eletrônica

---

**DEFENSE,A#**

Onde:

**DEFENSE:** Descreve o comando a ser enviado

**A:** Delay (1 a 60 minutos)

Exemplo: **DEFENSE,10#**

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### Consulta

**Para consulta, enviar:** **DEFENSE#**

## Tempo de vibração do sensor

---

Quando detectada uma vibração durante "x" tempo, há geração de evento. Para configurar a função, utiliza-se o comado:

**SENSOR,A,B,C#**

Onde:

**SENSOR:** Descreve o comando a ser enviado;

**A:** Tempo de detecção, 10 a 300 segundos;

**B:** Delay para alerta, 10 a 300 segundos;

**C:** intervalo de alerta entre as vibrações, 1 a 3000 minutos;

Exemplo: **SENSOR,5,30,1#**

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### **Consulta**

**Para consulta, enviar: SENSOR#**

## Tempo de GPS por vibração

---

Quando detectada uma vibração durante "x" tempo, o GPS pode ser iniciado. Para configurar a função, utiliza-se o comado:

**SENDS,A#**

Onde:

**SENDS:** Descreve o comando a ser enviado;

**A:** 0 a 300 minutos, tempo de detecção de vibração;

Exemplo: **SENDS,5#**

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### **Consulta**

**Para consulta, enviar: SENDS#**

## Bloqueio

---

Para utilização de saída para relé, é utilizado o seguinte comando:

**RELAY,C#**

Onde:

**RELAY:** Descreve o comando a ser enviado;

**C:** 0/1；

- 0: conexão gasolina/eletricidade;
- 1: corte de eletricidade/gasolina；

Exemplo: **RELAY,1#**

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

**OBS:. Para envio via SMS o número de telefone deve estar cadastrado na central (comando CENTER) ou não irá realizar o bloqueio.**

### **Consulta**

**Para consulta, enviar: RELAY#**

## Acionamento saída 2

---

Podendo ser utilizada como saída alternativa a saída de relé. Para isso configura-se o seguinte comando:

**OUT2,C#**

Onde:

**OUT2:** Descreve o comando a ser enviado;

**C:** Acionamento (0/1):

- 0: significa restaurar o relé;
- 1: significa desligar o relé；**padrão: 0.**

Exemplo: **OUT2,1#**

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### **Consulta**

**Para consulta, enviar: OUT2#**

## Criação de cerca

---

**Para cerca circular:**

**FENCE,B,0,D,E,F,X,M#**

Onde:

**FENCE:** Descreve o comando a ser enviado;

**B:** ON/OFF

- ON: alarme de cerca ligado
- OFF: alarme de cerca desligado

**0:** Definição de cerca circular;

**D:** Latitude;

**E:** Longitude;

**F:** Raio ( 1-9999 metros);

**X:** IN/OUT

- IN: alarmante ao entrar na cerca;
- OUT: alarmante ao sair da cerca;
- em branco significa alarmante ao entrar ou sair da cerca, Padrão: em branco.

**M:** Forma de aviso de alarme:

- 0: GPRS;
- 1: GPRS+SMS;

Exemplo: **FENCE,ON,0,-23.525339,-46.679023,3,IN,1#**

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### **Consulta**

**Para consulta, enviar: FENCE#**

---

Para cerca **retangular**:

**FENCE,B,1,D,E,F,G,X,M#**

Onde:

**FENCE:** Descreve o comando a ser enviado;

**B:** ON/OFF;

- ON: alarme de cerca ligado
- OFF: alarme de cerca desligado

**1:** Definição de cerca retangular;

**D:** Latitude do ponto 1 (-90 a 90 graus);

**E:** Longitude do ponto 1 (-180 a 180 graus);

**F:** Latitude do ponto 2 (-90 a 90 graus);

**G:** Longitude da posição 2, (-180 a 180 graus), a latitude suporta "N / S" ou "+/-" antes de seu valor, a longitude suporta "E / W" ou "+/-" antes de seu valor;

**X:** IN/OUT

- IN: alarmante ao entrar na cerca;
- OUT: alarmante ao sair da cerca;
- em branco significa alarmante ao entrar ou sair da cerca, Padrão: em branco.

**M:** Forma de aviso de alarme:

- 0: GPRS;
- 1: GPRS+SMS;
- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### Consulta

**Para consulta, enviar:** **FENCE#**

## Alarme de vibração

---

**SENALM,A,M#**

Onde:

**SENALM:** Descreve o comando a ser enviado

**A:** ON/OFF, Padrão: OFF;

**M:** 0/1/2/3, forma de alarme,

- 0: GPRS apenas;
- 1: SMS + GPRS;
- 2: GPRS + SMS + chamada telefônica;
- 3: GPRS + CALL, Padrão: 0;

Exemplo: **SENALM,ON,0#**

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### **Consulta**

**Para consulta, enviar:** **SENALM#**

## Alarme de bateria baixa

---

**BATALM,A,M#**

Onde:

**BATALM:** Descreve o comando a ser enviado;

**A:** ON/OFF

**M:** forma de alarme (0/1)

- 0: GPRS apenas
- 1: SMS + GPRS, Padrão: 1;

Exemplo: **BATALM,ON,0#**

Para desabilitar o alarme de bateria baixa: **BATALM,OFF#**

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### **Consulta**

**Para consulta, enviar: BATALM#**

## Configuração de SOS (Pânico)

---

Define a configuração para acionamento de alarme para SOS, para configura-lo utiliza-se o seguinte comando:

**SOSALM,A,M#**

Onde:

**SOSALM:** Descreve o comando a ser enviado;

**A:** ON/OFF, **Padrão: OFF**

**M: F**orma de alarme **(**0/1/2/3);

- 0: GPRS apenas,
- 1: SMS + GPRS,
- 2: GPRS + SMS + chamada telefônica,
- 3: GPRS + CHAMADA, **Padrão: 2**

Exemplo: **SOSALM,ON,0#**

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### **Consulta**

**Para consulta, enviar: SOSALM#**

## Odômetro

---

Para inserção de valores de odometro, o comando para sua configuração é:

**MILEAGE,A,B#**

Onde:

**MILEAGE:** Descreve o comando a ser enviado;

**A:** Ativa/desativa contagem de odometro, **padrão: OFF**

**B:** Valor inicial de odometro, (0 a 999999 km), **padrão: 0**

Exemplo: **MILEAGE,ON,1000#**

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### Consulta

**Para consulta, enviar:** MILEAGE#

## Alarme de movimento

---

Para identificação e envio de alarme devido a movimentação do dispositivo, utiliza-se o seguinte comando:

**MOVING,A,R,M#**

Onde:

**MOVING:** Descreve o comando a ser enviado

**A:** ON/OFF, **Padrão: OFF**

**R:** Raio de movimentação (100 a 1000 metros), **Padrão: 300 metros**

**M:** Forma de alarme **(**0/1/2/3);

- 0: GPRS apenas,
- 1: SMS + GPRS,
- 2: GPRS + SMS + chamada telefônica,
- 3: GPRS + CHAMADA, **Padrão: 1**

Exemplo: **MOVING,ON,300,0#**

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### Consulta

**Para consulta, enviar:** **MOVING#**

## Alarme de excesso de velocidade

---

Define os parâmetros para detecção de excesso de velocidade. Para a geração de alarme, utiliza-se o seguinte comando:

**SPEED,A,B,C,M#**

Onde:

**SPEED:** Descreve o comando a ser enviado

**A:** ON/OFF, Ativa ou desativa o alarme, **Padrão: OFF**

**B:** Range do tempo tempo de detecção (5 a 600 segundos), **Padrão: 20**

**C:** Limite de velocidade (1 a 255 km/h), **Padrão: 100**

**M:** Forma de alarme **(**0/1/2/3);

- 0: GPRS apenas,
- 1: SMS + GPRS,
- 2: GPRS + SMS + chamada telefônica,
- 3: GPRS + CHAMADA, **Padrão: 1**

Exemplo: **SPEED,ON,5,60,0#**

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### **Consulta**

**Para consulta, enviar: SPEED#**

## Sensor de porta

---

Define a forma de detecção de acionamento do sensor de porta.

**DOOR,X#**

Onde:

**DOOR:** Descreve o comando a ser enviado;

**X:** Trigger de detecção (0/1)

- 0: trigger negativo
- 1: trigger positivo; **Padrão: 1**
- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### Consulta

**Para consulta, enviar:** **DOOR#**

## Alarme de sensor de porta

---

Configuração para definir os critérios de geração do alarme de acionamento de porta

**DOORALM,A,B#**

Onde:

**DOORALM:** Descreve o comando a ser enviado;

**A:** Habilita/desabilita alarma: ON/OFF

**M:**  Forma de alarme **(**0/1/2);

- 0: GPRS apenas,
- 1: SMS + GPRS,
- 2: GPRS + SMS + chamada telefônica, **padrão: 1**

### Consulta

**Para consulta, enviar:** **DOORALM#**

## Sensibilidade de sensor

---

**LEVEL,A#**

**Onde:**

**LEVEL:** Descreve o comando a ser enviado;

**A:** Range de sensibilidade (1 a 5), **Padrão: 2**

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### Consulta

**Para consulta, enviar: LEVEL#**

## Alarme de curva brusca

---

Configuração realizada para definir os limites para identificação de mudança de trajeto brusca. O comando para configuração é:

**SWERVE,A,M,A,S,T#**

Onde:

**SWERVE:** Descreve o comando a ser enviado

**A:** Ativa/desativa alarme, ON/OFF, **padrão: OFF**

**M:** Forma de alarme **(**0/1/2);

- 0: GPRS apenas,
- 1: SMS + GPRS,
- 2: GPRS + SMS + chamada telefônica, **padrão: 0**

**A:** Ângulo para geração de alarme, 10 a 180 graus, **padrão: 30**

**S:** Velocidade para geração de alarme, 10 a 200 km/h, **padrão: 60**

**T:** Tempo de duração para detecção, 1 a 30 segundos, **padrão: 3**

Exemplo: **SWERVE,ON,0,10,10,1#**

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### **Consulta**

**Para consulta, enviar:** **SWERVE#**

## Alarme de mudança brusca de velocidade

---

Configuração realizada para definir os limites para identificação de aceleração e frenagem bruscas. O comando para configuração é:

**SPEEDCHECK,A,M,T,ΔV1,ΔV2#**

Onde:

**SPEEDCHECK:** Descreve o comando a ser enviado

**A:** Ativa/desativa alarme, ON/OFF, **padrão: OFF**

**M:** Forma de alarme **(**0/1);

- 0: GPRS apenas,
- 1: SMS + GPRS, **padrão: 0**

**T:** Tempo de duração para detecção, 1 a 30 segundos, **padrão: 4**

**ΔV1:** Delta de variação para aceleração, 10 a 300 km/h, **padrão: 30 km/h**

**ΔV2:** Delta de variação para desaceleração, 10 a 300 km/h, **padrão: 50 km/h**

Exemplo: **SPEEDCHECK,ON,0,1,10,10#**

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### **Consulta**

**Para consulta, enviar: SPEEDCHECK#**

## Alarme de colisão

---

Configuração realizada para definir os limites para identificação de possível colisão. O comando para configuração é:

**COLLIDE,A,M,V#**

**Onde:**

**COLLIDE:** Descreve o comando a ser enviado****

**A:** Ativa/desativa alarme, ON/OFF, **padrão: OFF**

**M:** Forma de alarme **(**0/1);

- 0: GPRS apenas,
- 1: SMS + GPRS, **padrão: 0**

**V:** Intensidade de colisão, 10 a 1024, **padrão: 800**

- A sensibilidade é utilizada para acionar o alerta de colisão. Reduzir a sensibilidade torna mais fácil ativar o alerta.

Exemplo: **COLLIDE,ON,0,10#**

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### **Consulta**

**Para consulta, enviar: COLLIDE#**

## Alarme de corte de energia

---

Comando utilizado para geração de alerta em ocasiões de ausência de alimentação repentina. Para configuração do alarme, o comando utilizado é:

**POWERALM,A,M,T1,T2#**

Onde:

**POWERALM:** Descreve o comando a ser enviado

**A:** Habilita/desabilita alarma: ON/OFF

**M:**  Forma de alarme **(**0/1/2);

- 0: GPRS apenas,
- 1: SMS + GPRS,
- 2: GPRS + SMS + chamada telefônica, **Padrão: 2**

**T1:** Tempo de detecção do corte (0-60 segundos), **Padrão: 5**

**T2:** “menor tempo de carregamento” (0-3600 segundos), **Padrão: 300**

Exemplo: **POWERALM,ON,0,5,300#**

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### **Consulta**

**Para consulta, enviar: POWERALM#**

## Ativar/Desativar LEDs

---

**LEDSLEEP,A#**

Onde:

**LEDSLEEP**: Descreve o comando a ser enviado;

A: Habilita/desabilita o modo de suspensão de led: ON/OFF

- **ON:** Quando o dispositivo está carregando, a luz apaga após 5 minutos; Quando o GPS está funcionando, a vibração não pode despertar a luz; quando o gps está desligado, o choque pode despertar a luz.
- **OFF:** Todas as luzes estão sempre acesas, **Padrão: ON**

Exemplo: **LEDSLEEP,ON#**

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### **Consulta**

**Para consulta, enviar: LED#**

## **Efeito estrela**

---

**SF,A#**

Onde:

A: Habilita/Desabilita(**ON/OFF**)

- **ON**: O equipamento irá ativar o efeito estrela, ou seja, em caso onde o equipamento estiver parado, as posições serão filtradas.
- **OFF:** O equipamento não irá filtrar as posições paradas e assim enviá-las para a plataforma.
    - **Padrão: ON**

****Exemplo: **SF,OFF#**

**Para consulta, enviar:** **SF#**

- Pode ser enviado por: **#SMS #SERVIDOR**

## Envio de tensão de bateria externa

---

**ADT,A,B#**

Onde:

**ADT:** Descreve o comando a ser enviado

**A:** Upload de dados ADT, ON/OFF,  **padrão: OFF**

**B:** Intervalo de tempo para Upload, 5 a 3600 segundos, **padrão: 600 segundos**

Exemplo:

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### Consulta

**Para consulta, enviar:** **ADT#**

## Envio de tensão de bateria externa

---

**ADT,A,B#**

Onde:

**ADT:** Descreve o comando a ser enviado

**A:** Upload de dados ADT, ON/OFF,  **padrão: OFF**

**B:** Intervalo de tempo para Upload, 5 a 3600 segundos, **padrão: 600 segundos**

Exemplo:

- Pode ser enviado por: **#SMS #SERVIDOR #SERIAL**

### Consulta

**Para consulta, enviar:** **ADT#**

## Buzzer

---

**SPEED,A,T,V,M,B#**

Onde:

A = ON/OFF, Ativa ou desativa a função do Buzzer, Padrão: OFF

T = Tempo para a detecção (1 a 30 segundos), Padrão: 4 segundos

V = Define a velocidade em que o Buzzer será acionado (10 a 200km/h), Padrão: 60km/h

M = Formas de aviso de alarme: 0/1, Padrão: 0

- 0: GPRS
- 1: SMS+GPRS

B = Abre ou fecha a saída do Buzzer: ON/OFF, Padrão: ON

Saida utilizada DOUT do EXT

Exemplo:

- **SPEED,ON,5,60,1,ON#**

### Consulta

**Para consulta, enviar: SPEED#**

## Restaurar para os padrões de fábrica

---

Para formartar o equipamento, utilize o seguinte comando:

**FACTORY#**