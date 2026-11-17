# Guia de comandos colaborativo da OLT Fiberhome

Esse guia tem como objetivo ser uma fonte de apoio para interação na interface de texto das OLTs Fiberhome.

Sempre que é necessário fazer qualquer intervenção nas OLTs da Fiberhome temos bastante dificuldades em encontrar os caminhos e comandos na rede, como sabemos que as OLTs fiberhome são populares entre provedores no Brasil, estaremos disponibilizando esse guia com alguns comandos utilizados, explicitando os casos de uso e algumas explicações de conceitos necessários para o entendimento.

Este guia tanto quanto os outros estão aqui para serem construídos de forma colaborativa e a lista de comandos crescerá até o ponto que teremos uma documentação robusta com todas as funções.

A OLT Fiberhome utiliza-se de diretórios para para dividir áreas 

## Acesso usuário comum

### ENABLE
-   Esse comando garante privilégios de administrador para o usuário, é necessário ter acesso as credenciais do administrador, pode ser abreviado com _EN_

## Acesso administrador
### ADMIN

#### showcard

-   Esse comando apresenta o estado atual de todos os slots 

#### show cpu {N_FRAME/N_SLOT}

-   Apresenta o uso da cpu da placa escolhida, se nenhuma placa for escolhida é impresso o uso de todas as placas

#### show cpu-mim {N_FRAME/N_SLOT}

-   Apresenta o usdo da cpu e memória da placa escolhida, se nenhuma placa for escolida é impresso o uso de todas as placas

#### show mac-address {FILTRO}

-   Apresena os mac-address aprendido pela OLT, é possível filtrar placa, vlan e porta, é possível também apresentar apenas a contagem de vlans encontradas

#### show running-config slot {N_SLOT} pon {N_PON} onu {N_ONU}

-   Esse comando apresenta a configuração atual de uma ONU específica

### ONU

#### show onu_state slot {N_SLOT} pon {N_PON} onu {N_ONU} 

-   Esse comando apresenta a lista de onus da pon especificada apresentando o número de identificação registrado para a ONU e o atual status.

#### show mac_list slot {N_SLOT} pon {N_PON} onu {N_ONU} port {N_PORTA_ONU}

-   Esse comando apresenta a lista de MACs enxergados na porta lan especificada da ONU especificada.

#### show onu_aaa_config slot {N_SLOT} pon {N_PON} onu {N_ONU}

-   Esse comando apresenta a configuração de AAA(Authentication, Authorization e Accounting) da ONU especificada.

#### show authorization slot {N_SLOT} pon {N_PON}

-   Esse comando apresenta a lsita de ONU autorizadas na PON específica apresentando, informando o número da ONU, tipo da ONU, ID físico e outros

#### show online slot {N_SLOT} pon {N_PON}

-   Esse comando apresenta as onu online de uma PON específica informando o id, tipo e principalmente serial

#### show onu optical-info slot {N_SLOT} pon {N_PON} onu all

-   Esse comando apresenta uma lista com o status e outras métricas de todas as ONU em uma PON específica, as variáveis podem ser substituídas por ALL para ver todas as ONUs

#### show mac-list slot {N_SLOT} pon {N_PON} onu {N_ONU} port {N_PORTA_ETHERNET}

-   Esse comando apresenta os MACs enxergados atrás da ONU especificada

### MAINTENANCE
   ### ALARM
    #### show alarm current obj 1/{N_SLOT}/{N_PON}/{N_ONU}

-   Esse comando apresenta os alarmes ativos na ONU especificada

### SERVICE

#### telnet slot {N_SLOT}

- Esse comando permite o usuário se conectar especificamente a um slot da OLT

### PON
> Esse comando funciona apenas quando conectado via TELNET a um slot
#### show optical_status olt ponno {N_PON}

- Esse comando informa status operacionais da pon como sinal do tranceiver e sinal das ONUs nessa pon.


