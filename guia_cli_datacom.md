# Guia de comandos DATACOM


#### show runing-config {ARG}
- O comando permite você veja qual é a configuração que está rodando atualmente, o campo de {ARG} pode ser alterado para um elemento específico, apresentando apenas a configuração atual daquele elemento. Também pode ser enviado o campo vazio, assim a OLT responde todas as configurações
- Ex. _show running-config interface gpon_ vai entregar todas a configurações vinculadas as interfaces gpon

#### show mac-address-table {FILTER}
- O comando imprime a tabela de endereços MAC enxergados no filtro específico. O comando sem filtro especificado devolve todos os endereços enxergados na OLT.
- Os filtros podem ser por _INTERFACE_, _MAC-ADDRESS_, _TYPE_ e _VLAN_.

#### show interface gpon {N_PON} onu {N_ONU}
- Esse comando imprime na tela informações básicas sobre a ONU especificada ou da interface especificada.
- os argumentos {N_PON} e {N_ONU} podem ser vazios, abordaremos com exemplos logo abaixo
- Ex. _show interface gpon_ apresenta informações de todas as pons
- Ex. _show interface gpon {N_PON}_ apresenta informações da pon 1 especificamente
- Ex. _show interface gpon onu_ apresenta informações de todas as ONUs de todas as PONs
- Ex. _show interface gpon {N_PON} onu_ apresenta informações de todas as ONU da PON especificada
- Ex. _show interface gpon {N_PON} onu {N_ONU}_ apresenta informações da onu especificada
