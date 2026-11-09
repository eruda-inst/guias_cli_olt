# Guia de comandos DATACOM

### Modo Exec
- Esse modo é o modo inicial de acesso a OLT, é sempre o primeiro nível ao fazer login. Permite apenas comandos de leitura.

#### {COMANDO} | include {ARG}

- Alguns comandos permite a inclusão do include após o pipe "|", o include funciona como um filtro para especificar uma parte do que deve ser impresso

#### show runing-config {ARG}
- O comando permite você veja qual é a configuração que está rodando atualmente, o campo de {ARG} pode ser alterado para um elemento específico, apresentando apenas a configuração atual daquele elemento. Também pode ser enviado o campo vazio, assim a OLT responde todas as configurações
- Ex. _show running-config interface gpon_ vai entregar todas a configurações vinculadas as interfaces gpon

#### show history
- Apresenta histórico de comandos

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

#### show log
- Apresenta o log de toda a OLT
- Pode ser utilizado como histórico de alarmes, através do filtro com _include_

#### show alarm
- Apresenta os alarmes atuais na OLT
- Permite uso do _include_ para filtrar ONU específica ou outro elemento

### Modo Config
- Esse é o modo privilegiado, aqui o usuário ganha acesso de adminitrador e pode escrever na OLT
- O modo privilegiado permite a navegação entre as sessões de configuração
- Ex. _interface gpon {N_PON}_ permite entrar na sessão para configuração da PON especificada

#### config
- Ativa o modo privilegiado

#### commit
- Salva as escritas feitas

#### no {COMANDO}
- O comando _no_ nega a existência de alguma configuração já escrita, apagando-a.


#### interface gpon {N_PON} onu {N_ONU}
- Insere uma nova nova ONU com o número especificado na pon especificada e entra na sessão de configuração desta nova ONU

#### name {NOME_ONU}
- Insere uma string para representar o nome da ONU
> ⚠️ ESSE COMANDO NECESSITA QUE O USUÁRIOE STEJA DENTRO DE UMA SESSÃO DE CONFIGURAÇÃO DE UMA ONU

#### serial_number {N_SERIAL}
- Vincula a ONU sendo provisionada a um serial
> ⚠️ ESSE COMANDO NECESSITA QUE O USUÁRIOE STEJA DENTRO DE UMA SESSÃO DE CONFIGURAÇÃO DE UMA ONU

#### line-profile {PROFILE}
- Vincula a ONU a um line profile pre configurado
> ⚠️ ESSE COMANDO NECESSITA QUE O USUÁRIOE STEJA DENTRO DE UMA SESSÃO DE CONFIGURAÇÃO DE UMA ONU

#### ethernet {N_PORTA_ETHERNET}
- Entra na sessão de configuração da porta ethernet da ONU especificada
> ⚠️ ESSE COMANDO NECESSITA QUE O USUÁRIOE STEJA DENTRO DE UMA SESSÃO DE CONFIGURAÇÃO DE UMA ONU

#### negotiation
- Habilita negociação na porta
> ⚠️ ESSE COMANDO NECESSITA QUE O USUÁRIOE STEJA DENTRO DE UMA SESSÃO DE CONFIGURAÇÃO DE UMA PORTA ETHERNET DE UMA ONU

#### no shutdown
- Habilita a porta
> ⚠️ ESSE COMANDO NECESSITA QUE O USUÁRIOE STEJA DENTRO DE UMA SESSÃO DE CONFIGURAÇÃO DE UMA PORTA ETHERNET DE UMA ONU

#### native vlan vlan-id {ID_VLAN}
- Vincula uma VLAN a porta
> ⚠️ ESSE COMANDO NECESSITA QUE O USUÁRIOE STEJA DENTRO DE UMA SESSÃO DE CONFIGURAÇÃO DE UMA PORTA ETHERNET DE UMA ONU

#### service-port {N_SERVICE_PORT}
- Inicia a configuração de uma service port indicando o número identificador dela.
- O comando pode ser enviado de forma completa, não necessitando quebras como apresentado nesse guia
- Ex. service-port {N_SERVICE_PORT} gpon {N_PON} onu {N_ONU} gem {N_GEM_PORT} match vlan vlan-id {ID_VLAN} action vlan replace vlan-id {ID_VLAN}

#### gpon {N_PON} onu {N_ONU} gem {N_GEM_PORT}
- Vincula a service-port a uma ONU e sua GEM PORT
> ⚠️ ESSE COMANDO NECESSITA QUE O USUÁRIOE STEJA DENTRO DE UMA SESSÃO DE CONFIGURAÇÃO DE UMA SERVICE-PORT

#### match vlan vlan-id {ID_VLAN}
- Vincula uma VLAN a essa service-port
> ⚠️ ESSE COMANDO NECESSITA QUE O USUÁRIOE STEJA DENTRO DE UMA SESSÃO DE CONFIGURAÇÃO DE UMA SERVICE-PORT

#### action vlan replace vlan-id {ID_VLAN}
- Indica a ação a ser feita com a vlan vinculada
> ⚠️ ESSE COMANDO NECESSITA QUE O USUÁRIOE STEJA DENTRO DE UMA SESSÃO DE CONFIGURAÇÃO DE UMA SERVICE-PORT

#### show interface gpon discovered-onus
- Comando imprime na tela as ONUs desautorizadas conectadas a OLT

