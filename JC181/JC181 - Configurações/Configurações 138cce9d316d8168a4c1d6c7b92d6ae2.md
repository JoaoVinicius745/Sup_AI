# Configurações

# Configurações Iniciais

Nessa etapa nós iremos mostrar o passo a passo inicial para ligar o equipamento e a configuração inicial!

**Nota:** Ao contrário de outras câmeras Jimi, a JC181 apenas utiliza cartões de até 128GB e de formato FAT32. Garanta que o cartão está formatado e tem tamanho menor ou igual ao limite ao ser inserido na câmera.

## 1 - Energizar

---

Energize a câmera com os seguintes fios:

| **Energia** | B+ | Vermelho | Fio positivo do equipamento, tensão 9-30v | **Obs: Nos fios do chicote tem uma marcação indicando qual a finalidade de cada fio!** |
| --- | --- | --- | --- | --- |
|  | GND | Preto | Fio negativo do equipamento |  |
|  | ACC | Amarelo | ACC |  |

![https://wiki-foconavia.newtectelemetria.com.br/jc181/cabo_181.png](https://wiki-foconavia.newtectelemetria.com.br/jc181/cabo_181.png)

## 2 - Configurações

---

**ATENÇÃO: Caso a plataforma de utilização não seja a TrackSolid, envie o comando: “COREKITSW,0” antes de realizar qualquer configuração, esse comando é utilizado para que o equipamento comunique corretamente com a plataforma.**

A primeira configuração a ser feita é a APN do CHIP, sem ela o equipamento não terá comunicação!

APN,APN,LOGIN,SENHA

APN - Apn que deseja configurar

LOGIN - Login que deseja configurar

SENHA - Senha que deseja configurar

### 3 - Status dos Leds

---

Os três LEDs na parte superior da câmera, logo acima da lente interna, são a principal forma de detecção de bom ou mau funcionamento do dispositivo. Na tabela abaixo, está o significado de cada um dos comportamentos possíveis.

![image.png](Configurac%CC%A7o%CC%83es%20138cce9d316d8168a4c1d6c7b92d6ae2/image.png)

### 4 - Teste em bancada

---

Uma vez que a JC181 não possui algoritmos de inteligência artificial, os testes de bancada são realizados para verificar o funcionamento das funções básicas de streaming, upload e eventos. Além de validar as configurações de conexão à internet e ao servidor utilizado.

Na imagem abaixo estão os componentes básicos para o teste. São eles:

1. O módulo da JC181;
2. Chicote de alimentação da JC181;
3. Conector P4 fêmea para conectar o chicote à fonte;
4. Chip de dados banda larga;
5. Cartão de memória de, no mínimo, 32GB;
6. Fonte de alimentação de 12V 2A, com conector P4 macho.

![https://wiki-foconavia.newtectelemetria.com.br/jc181/componentes_teste_bancada.jpg](https://wiki-foconavia.newtectelemetria.com.br/jc181/componentes_teste_bancada.jpg)

Para o teste em bancada, ***e somente para o teste em bancada***, é possível conectar a ignição ao positivo, e conectar o positivo, acc e negativo no conector P4, como na imagem abaixo.

![https://wiki-foconavia.newtectelemetria.com.br/jc181/conectorp4_jc181.jpg](https://wiki-foconavia.newtectelemetria.com.br/jc181/conectorp4_jc181.jpg)

Após isso, basta inserir o chip e o cartão de memória na câmera, ligar o chicote na câmera e o conector à fonte. Estará pronto então para realizar os testes.

![https://wiki-foconavia.newtectelemetria.com.br/jc181/setup_completo_181.jpg](https://wiki-foconavia.newtectelemetria.com.br/jc181/setup_completo_181.jpg)

### 5- Verificação do armazenamento em cartão de memória

---

**Para verificar que o cartão está presente e está sendo corretamente reconhecido pela câmera, deve-se usar o comando:** CAMERA,TF

O retorno será o status do cartão como no exemplo abaixo:

CAMERA TF:Normal,total:127061MB,free:127033MB

### 6- Habilitar o envio de posições

---

Caso o equipamento não esteja enviando as posições para a plataforma, envie o seguinte comando: GPSDUP,A#

Onde: A = ON/OFF

Sendo assim, envie o comando: GPSDUP,ON#

**Para consulta, enviar:** GPSDUP#

### 7- Desligar o filtro de efeito estrela

---

O filtro de efeito estrela serve para evitar que o equipamento, quando estiver parado, envie posições de GPS “aleatórias”. Isso acontece porque o posicionamento via GNSS está sujeito a imprecisões que ficam mais evidentes quando o veículo está parado. Mas esse filtro pode causar o não envio de posições, o que é indesejado para algumas operações.

O comando para desativar o efeito estrela é o SF,OFF

### 8- Operação contínua com a ignição desligada

---

Por padrão, a câmera entra em um estado de hibernação profunda ao ter a ignição desligada. Para que a câmera continue enviando posições de GPS e esteja sempre disponível para acessar o streaming nessas condições, é necessário enviar o comando PWRLIMIT,ON

***IMPORTANTE: Nesse estado, a câmera vai desligar os LEDs quando estiver com ignição desligada, mas continuará consumindo a bateria do veículo. A gravação contínua depende da ignição ligada, então apenas serão gravados os vídeos de eventos, como vibração e botão de SOS.***

### Comandos SMS/TCP

---

Os comandos podem ser enviados por SMS ou através do TCP (Servidor). No caso da JC181, não é necessário incluir a senha nos comandos enviados via SMS.

É importante ressaltar que nem todos os comandos são compatíveis com o envio via SMS, isso é feito com o intuito de proteger o equipamento de comandos que poderiam comprometer seu funcionamento.

# Consultas

---

## Firmware

---

**Para consulta, enviar:** VERSION#

**A resposta será no formato:**

[VERSION]C181_WAAP_LA_V2.3.3.4_240921.1453,[GK7205]C181_SGKS_ver_v1.6.0_240921.1527

C181_WAAP_LA_V2.3.3.4_240921.1453 - Versão de firmware do módulo de comunicação.

C181_SGKS_ver_v1.6.0_240921.1527 - Versão de firmware do módulo de vídeo

## Status

---

**Para consultar o status do equipamento, enviar:** STATUS#

**A resposta será no formato:** ext Battery:11.66V; GPRS:Link Up; GSM Signal Level:Strong; GPS:Successful positioning; SVS Used in fix:10(14); GPS Signal Level:40,14,35,23,39,17,40,34,29,19 ACC:ON; Defense:OFF; SIM:Normal;

ext Battery:11.66V; - Status da tensão de alimentação

GPRS:Link Up; GSM Signal Level:Strong - Status de conexão de chip.

GPS:Successful positioning; SVS Used in fix:10(14); GPS Signal Level:40,14,35,23,39,17,40,34,29,19 - Conexão de GPS.

ACC:ON;  - Status de ignição.

Defense:OFF;  - Se a câmera encontra-se em estado de defesa. O estado de defesa é o estado em que a câmera fica após alguns minutos com a ignição desligada. É nesse estado que são gerados alertas de vibração, que podem significar que alguém está tentando entrar no veículo ou que houve uma batida com o veículo estacionado.

SIM:Normal; - Estado do chip de dados

## Parâmetros

---

**Para consultar os parâmetros, enviar:** CHECK#

**A resposta será no formato:** IMEI:8612345678912345;VERSION:C181_WAAP_LA_V2.3.3.4_240921.1453;[GK7205]:C181_SGKS_ver_v1.5.2_240812.2030;SERVER:0,3.18.34.201,21122;BSERVER:0,0.0.0.0,0;GET IP:3.18.34.201;APN:tim.br,tim,tim;CSQ[4G]:18;GPRS:1;GPS:OFF;BDS:OFF;POWER:12.74;ACC:ON,4;Curr ACC:0;TIMER:10;SOS NUM:,,;IMSI:72123456789123;ICCID:8955123456789123456;Camera0:Normal;Camera1:Normal;T card:Error;Video switch:1;Record switch:1;SOSALM:ON;SENALM:2;COLLIDE:OFF;SPEED:OFF,0,50,20;SPEEDCHECK:OFF,0,4,30,50;SWERVE:OFF,0,30,60,3;BCD:0;URLTYPE:2;CPU temp:52;Relay:0;Local time: 2024-11-06 20:03:46;Local Timezone:W,4,0;SENSOR TYPE:Mira DA217;bootcase:Start_total: 214 Soft_crashes: 63 Wdt_or_Power: 86 Use_restart: 26 unknow_start: 39 Cmd_restart: 18 ;currcase:Wdt_or_Power(10);HBTCTL:1;

# Configuração de rede

---

## APN

---

A primeira configuração a ser feita é a APN do CHIP, sem ela o equipamento não terá comunicação!

APN,APN,LOGIN,SENHA

APN - Apn que deseja configurar

LOGIN - Login que deseja configurar

SENHA - Senha que deseja configurar

## Servidor

---

**Para configurar o servidor, envie:** SERVER,A,B,C

A = IP(0) ou Domínio(1)

B = Servidor

C = Porta de conexão

Exemplo: SERVER,1,iothub.jimibrasil.com.br,21122 **ou** SERVER,0,3.18.34.201,21122

**Para consultar o servidor atual, enviar:** SERVER#

**A resposta será:** SERVER:1,iothub.jimibrasil.com.br,21122 ou SERVER:0,3.18.34.201,21122

iothub.jimibrasil.com.br - Local configurado para envio de dados

21122 - Porta configurada

**Para o equipamento comunicar corretamente com o servidor, envie:**

**URLTYPE,2** para utilizar o equipamento nas plataforma que não sejam a TRACKSOLID

**URLTYPE,1** para utilizar o equipamento na plataforma da TRACKSOLID

## Ativar/Desativar HOTSPOT

---

**Para ativar o hotspot da JC181, envie:** WIFIAP,A

A: ON/OFF

**Padrão:** OFF

**Senha para conectar no Wi-Fi:** 8 últimos do IMEI do equipamento

## **WIFI**

---

**Para configurar o WIFI da JC181, envie:** SSID,A,B,C

**Obs:** Para utilizar o WIFI, o hotspot deve estar desativado.

A = ON/OFF

B = Nome do WIFI

C = Senha (É necessário ter uma senha definida)

**Exemplo:** SSID,ON,JIMI,JIMI.123

Obs.: O nome e a senha devem possuir no máximo 10 caracteres cada. Não são aceitos espaços no nome da rede.

# Posição

---

## Posição

---

**Para configurar o tempo de envio de posição, envie:** TIMER,A

A **= 1-18000**

**Padrão** = 10s

**Para consulta, envie:** TIMER

## Posição por ângulo

---

**Para configurar o envio de posição por ângulo, envie:** ANGLEREP,A,B,C

A **= ON,OFF, liga ou desliga a função**

**B = 5-180, mudança de ângulo, em graus, para detectar a curva**

**C = 2-5, tempo em segundos em que deve ocorrer a mudança de B graus para detectar a curva e enviar a posição**

**Padrão: ON,30,3**

**Para consulta, envie:** ANGLEREP

# Configuração da câmera

---

## Reiniciar

---

**Para reiniciar o equipamento, envie:** RESET

**A resposta será:** RESET set OK!The terminal will restart after 20 seconds!

## Restaurar

---

**Para restaurar o equipamento para as configurações de fábrica, envie:** FACTORY

**A resposta será:** OK!

**Este comando apaga todas as configurações embarcadas ( APN..,) e redefine o equipamento para as configurações de fábrica!**

## Resolução

---

**Para configurar a resolução de gravação das imagens no equipamento, envie:** VIDEO,PARAM,1,A,B,C

A **= 480/720/1080, resolução de vídeo.**

B **= 30/25/15, taxa de quadros do vídeo.**

C = **1-8, taxa de bits do vídeo, em Megabits.**

**Padrão = 720,25,4**;

## Volume

---

**Para configurar o volume do equipamento, envie:** VOLUME,A

A **= Intensidade do volume**

0 = Desligado

1 = Baixo

2 = Médio

3 = Alto

**Padrão = 2**

**Para consultar o volume atual:** VOLUME

## Fuso horário

---

**Para alterar o fuso horário do equipamento, envie:** GMT,A,B,C

A **= E/W, E se o fuso horário for positivo ou W se for negativo**

B = **0-12, fuso horário**

C **= 0/15/30/45, para locais que têm o fuso horário quebrado**

**Exemplo: GMT,W,3,0 (para o fuso horário de Brasília -03:00**

**Padrão: E,8,0**

**Para consultar o fuso horário atual, envie:** GMT

## Bloqueio

---

**Para ativar/desativar o bloqueio do veículo, envie:** RELAY,A

A **= 0/1**

0 = Bloqueio inativo.

1 = Bloqueio ativo.

## Formatar o cartão de memória

---

**Para formatar os cartões de memória, envie:** CAMERA,TF,FORMAT

Resposta: CAMERA TF set OK, TF Format begin, do not close camera power!

## Tempo para desligar o GPS

---

Após "x" tempo sem nenhuma vibração, o GPS será desligado. Para configurar a função, utiliza-se o comado:

SENDS,A#

Onde:

SENDS**:**Descreve o comando a ser enviado;

A: 0 a 300 minutos, tempo de detecção de vibração;

Exemplo: **SENDS,5#**

## **Ativar/Desativar o envio de posições**

---

Para envio de dados com informações GPS, utilize o comando:

GPSDUP,A#

A = ON/OFF

Exemplo: GPSDUP,ON#

**Para consulta, enviar:** GPSDUP#

# Configuração de eventos

---

## Excesso de velocidade

---

**Para configurar o alarme de velocidade excedida, envie:** SPEED,A,B,C,D

**A** **= ON/OFF**

**B = 0: GPRS**

**C = 1 - 255:** Limite de velocidade - Padrão: 50 - Unidade: km/h

**D = 5 - 600:** Tempo de detecção - Padrão: 20 - Unidade: Segundos

## Vibração

---

**Defina os parâmetros de condição para o dispositivo acionar o alerta de vibração, quando o veículo estiver estacionado, envie:** SENALM,A,B,C,D

A **= 0-5, sensibilidade, em que 0 desativa o alarme.**

**B = 1-20, número de vibrações necessárias para ativar alarme.**

**C = 1-3000, tempo de detecção, em segundos, em que devem acontecer B vibrações.**

**D = 1-3000, tempo de filtro, em minutos, ou intervalo mínimo entre dois alarmes.**

**Padrão = 2,5,10,15**

**Para consultar, envie: SENALM**

## Colisão

---

**Para configurar o envio de eventos de colisão, envie:** COLLIDE,A,B,C,D,E,F

**A = ON/OFF** - Liga ou desliga o alarme.

**B = 0** - Modo de envio do alerta - 0: GPRS.

**C = 0-255**- Sensibilidade para a detecção de colisão, configurando o nível em que o sistema detecta uma colisão com base na força do impacto.

**D = 3-20** - Reservado para uso futuro, atualmente não possui função; Manter no valor padrão: 10 segundos.

**E = 10-90** - **(Tempo de detecção de velocidade do veículo)**: Quando o sistema suspeita de uma possível colisão, ele aguarda este período de tempo antes de verificar a velocidade do veículo; Valor padrão: 20 segundos.

**F = 5-30** - **(Velocidade mínima para confirmar colisão)**: Após o tempo **E**, se a velocidade do veículo estiver abaixo do limite **F**, a situação é confirmada como uma colisão real. Caso contrário, é considerado um alarme falso e a gravação do vídeo é mantida localmente, sem o envio do alerta; Valor padrão: 5 km/h.

**Para consultar, envie: COLLIDE**

## Aceleração e Frenagem Brusca

---

**Para configurar o envio de eventos de aceleração e frenagem brusca, envie:** SPEEDCHECK,A,B,C,D,E

A **= ON/OFF, liga ou desliga o alarme**

**B = 0, modo de envio do alerta - 0: GPRS**

**C = 1-30, tempo de detecção, em segundos.**

**D = 10-300, aumento de velocidade, em km/h, em C segundos para determinar uma aceleração brusca.**

**E = 10-300, diminuição de velocidade, em km/h, em C segundos para determinar uma frenagem brusca.**

Padrão: OFF,0,4,30,50

**Para consultar, envie: SPEEDCHECK**

## Curva Brusca

---

**Para configurar o envio de eventos de curva brusca, envie:** SWERVE,A,B,C,D,E

A **= ON/OFF, liga ou desliga o alarme**

**B = 0, modo de envio do alerta - 0: GPRS**

**C = 10-180, mudança de ângulo, em graus, para determinar curva brusca.**

**D = 10-300, limite de velocidade, em km/h, para determinar uma curva brusca.**

**E = 1-30, tempo de detecção, em segundos, para determinar uma curva brusca.**

Padrão: OFF,0,30,60,3

**Para consultar, envie: SWERVE**