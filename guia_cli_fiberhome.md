# Guia de comandos colaborativo da OLT Fiberhome

Esse guia tem como objetivo ser uma fonte de apoio para interação na interface de texto das OLTs Fiberhome.

Sempre que é necessário fazer qualquer intervenção nas OLTs da Fiberhome temos bastante dificuldades em encontrar os caminhos e comandos na rede, como sabemos que as OLTs fiberhome são populares entre provedores no Brasil, estaremos disponibilizando esse guia com alguns comandos utilizados, explicitando os casos de uso e algumas explicações de conceitos necessários para o entendimento.

Este guia tanto quanto os outros estão aqui para serem construídos de forma colaborativa e a lista de comandos crescerá até o ponto que teremos uma documentação robusta com todas as funções.

A OLT Fiberhome utiliza-se de diretórios para para dividir áreas 

## ONU

### show onu_state slot [N_SLOT] pon [N_PON] onu [N_ONU] 

-   Esse comando apresenta a lista de onus da pon especificada apresentando o número de identificação registrado para a ONU e o atual status.

### show mac_list slot [N_SLOT] pon [N_PON] onu [N_ONU] port [N_PORTA_ONU]

-   Esse comando apresenta a lista de MACs enxergados na porta lan especificada da ONU especificada.

### show onu_aaa_config slot [N_SLOT] pon [N_PON] onu [N_ONU]

-   Esse comando apresenta a configuração de AAA(Authentication, Authorization e Accounting) da ONU especificada.



