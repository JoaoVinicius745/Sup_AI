# Características

# Características gerais do produto

---

O LL303 é um rastreador solar 4G projetado para o gerenciamento de veículos e embarcações de construção. Com painel solar, carregador magnético e classificação IP67 à prova d'água, este dispositivo é ideal para uma variedade de implantações que requerem longo tempo de uso e desempenho contínuo ótimo. A comunicação LTE com fallback GSM (2G) garante uma conexão sólida em quase todos os casos. Além desses recursos, vários modos de trabalho, vários acessórios periféricos e o conjunto de alertas acionados por eventos tornarão o LL303 uma parte valiosa de sua estratégia de gerenciamento de frota.

- Comunicação através de redes 4G LTE com fallback para GSM 2G
- Carregamento Solar e Magnético
- Alertas Múltiplos
- Posicionamento GPS, BDS e LBS
- Resistência à poeira e à água IP67
- Múltiplos Modos de Funcionamento

![https://wiki.jimibrasil.com.br/ll303/hardware1.png](https://wiki.jimibrasil.com.br/ll303/hardware1.png)

![https://wiki.jimibrasil.com.br/ll303/hardware2.png](https://wiki.jimibrasil.com.br/ll303/hardware2.png)

# Alimentação

---

**Bateria**

- 10,000 mAh/3.7V

**Energia solar**

- 5V/400mA (Tensão/Corrente de Operação Padrão @STC)
- STC: Iluminação direta com lâmpada halógena de 38.000Iux no banco de testes

**Carregador magnético**

- 5V/2A

# Rede celular

---

| **Rede de comunicação** | LTE Cat 1/GSM | LTE Cat M1/Cat NB2 |
| --- | --- | --- |
| **Frequência** | **LL303-L**
LTE-FDD: B1/B2/B3/B4/B5/B7/B8/B20/B28
LTE-TDD: B40 
GSM: B2/B3/B5/B8 | **LL303-A**
Cat M1: B2/B4/B5/B12/B13/B25/B26/B66
Cat NB2: B2/B4/B5/B12/B13/B25/B66
GSM: B2/B3/B5/B8 |
|  | **LL303-E**
LTE-FDD: B1/B3/B5//B7/B8/B20/B28
LTE-TDD: B38/B40/B41 
GSM: B2/B3/B5/B8 |  |

**SIM CARD:** Nano-SIM

# GNSS

---

| Sistema de posicionamento | GPS+BDS+ LBS |
| --- | --- |
| Precisão de posicionamento | < 2.5m CEP |
| Sensibilidade de rastreamento | -165dBm |
| Sensibilidade de aquisição | -I48dBm |
| TTFF (Céu aberto) | Início rápido médio 1seg |
|  | Início a frio médio 32seg |

# Temperatura de operação e proteção

---

**Temperatura de operação: -**20°C à + 70°C

**Umidade de operação:** 5% ~ 95%, sem condensação

**Índice de proteção:**  IP67

# Características

---

| Sensores | Acelerômetro, sensor de efeito Hal |
| --- | --- |
| Cenários | Alerta de bateria fraca, alerta de violação, alerta de vibração |
| Bluetooth | BLE 5.0 |
| RFID | 2,4 GHz |

# LED Status

---

## Verde (Celular) – Status

---

**Piscando rápido [0,35-0,3s (ligado-desligado)]** - Inicialização de rede

**Piscando lentamente [0,1s-3s (ligado-desligado)]** - O dispositivo está on-line

**Led verde fixo** - Nenhum cartão SIM

**Piscando lentamente [1s-3s (ligado-desligado)]** - Não foi possível conectar-se à plataforma

## Vermelho (Status de energia/Ligado)

---

**Piscando rápido [0,35-0,3s (ligado-desligado)]** - A bateria está fraca

**Piscando lentamente [0,3s-3s (ligado-desligado)]** - O carregamento está completo

**Fixo** - Carregamento do dispositivo (via cabo)

**Piscando lentamente [0,3s-5s (ligado-desligado)]** - Carregamento (via energia solar)

**Desligado** - A bateria está descarregada ou encontra uma falha interna

# Instalação e uso

---

### Instalação

---

Fixe a base na posição de instalação com parafusos. Em seguida, monte o dispositivo na base e fixe-os com parafusos.

### Anexo de cartão SIM

---

**Passo 1:** Prepare um cartão SIM adequado.

O tamanho do cartão é o seguinte:

![https://wiki.jimibrasil.com.br/ll303/tamanho_chip.png](https://wiki.jimibrasil.com.br/ll303/tamanho_chip.png)

**Passo 2:** Remova o tampão de borracha à prova d'água na lateral e insira o cartão SIM no lugar, conforme mostra a figura a seguir:

(**Nota:** O dispositivo deve ser desligado antes de remover o SIM, caso contrário, o SIM poderá ser queimado.)

![https://wiki.jimibrasil.com.br/ll303/passo_2.png](https://wiki.jimibrasil.com.br/ll303/passo_2.png)

### Ligar e desligar

---

Ligue ou desligue o dispositivo usando o botão liga/desliga.

### Carregando

---

Conecte o dispositivo com um carregador 5V/2A (que deve ser adquirido separadamente). O LED fica aceso quando o dispositivo está carregando e pisca lentamente quando o carregamento é concluído .

![https://wiki.jimibrasil.com.br/ll303/carregador.png](https://wiki.jimibrasil.com.br/ll303/carregador.png)

## Modos de trabalho

---

| **Gps normal** | Neste modo, o dispositivo sempre tem seus serviços de rede habilitados e fará upload de dados de localização em um intervalo fixo, que pode ser configurado através da plataforma de serviço de localização ou aplicativo móvel especificado pelo seu revendedor. |
| --- | --- |
| **Posicionamento inteligente** | Neste modo, o dispositivo pode reconhecer automaticamente as condições atuais de localização e o status de atividade do veículo no qual está instalado e escolher de forma inteligente um sistema de posicionamento e um intervalo de upload. |
| **Economia de energia** | O dispositivo irá acordar em um determinado intervalo configurado para fazer upload de dados de localização. Após a conclusão de cada upload, o dispositivo entrará em suspensão profunda e não executará nenhuma consulta remota ou definirá ações. |

## Observações:

---

- Use baterias especificadas pelo fabricante do dispositivo. O fabricante não assumirá qualquer responsabilidade de reparação por danos resultantes da utilização de acessórios não originais.
- Evite objetos metálicos, pois podem causar curto-circuitos nos contatos da bateria.
- Não dobre nem abra a bateria à força.
- Não mergulhe a bateria em água nem a exponha ao fogo.
- É proibido usar baterias deformadas, descoloridas, derramadas ou danificadas na embalagem.
- É proibido desmontar ou modificar a bateria.