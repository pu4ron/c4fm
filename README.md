# PIVoiceBrasil - v2.4 (PU4RON - RONUALDO)

***O 'pivoicebrasil' é um conjunto de ferramentas cuja a função é ativar, automatizar e possibilitar os diversos recursos do pi-star. Por exemplo, uso de dg-id(s) por equipamentos DMR em modo cross-over (DMR2YSF), ativar e desativar redes DMR e modos via rádio e tantas outras funções... Vale lembrar também os diversos tipos de controles que as ferramentas disponibilizam aos usuários via rádio e aplicativo (app) para  gerencia do pi-star.***
 
# Novo! (12.02.2022) Lookup para escolha de servidores de consulta: QRZ.com ou RadioID. "Expert/Tools:CSS Tool"

![F1](https://user-images.githubusercontent.com/40077152/153916581-1085a86c-1f10-4cf0-b69f-63b5128bc332.png)


# Leia-me: 

* -> 1.0 - Update. Não continue sem atualizar seu pi-star.
* -> 1.1 - Ative "DMR2YSF".
* -> 1.2 - Selecione um servidor com suporte DG-ID.
* -> 1.3 - Faça backup do seu pi-star.
* -> 1.4 - Ative o SSH.

* Script baseado na versão 4 do pi-star.
* Servidor de referência em cross-mode(DMR2YSF): "YSF72401-BR-C4FM-Brasil-YCS724" (Default). Painel: http://ycs724.amrase.org.br/ycs/
* Outros servidores podem ser utilizados pelo usuário, com ou sem suporte a dg-id.
* Suporte a servidores YSF.

* Para uso via celular instale o app ***(SSH button)*** que irá criar os botões para executarem os comandos solicitados... 
* Lembrando que os mesmos comandos executados no aplicativo também podem ser executados no terminal shell do pi-star.

# App 'SSH button' - configuração:

* -> Label: nome do comando ou DG-ID.
* -> Command: comando a ser executado. => sudo c4fm + (DG-ID)  / sempre dois digitos: 01,02,72,96 etc...  

* Ex: sudo c4fm 72          (DG-ID 72)
* Ex: sudo c4fm off         (Disconnect) 
* Ex: sudo c4fm reset       (Reset: retorna as configurações definidas pelo usuário em 'Expert, YSF GW, Options')

* -> SSH hostname: ip da raspberry.
* -> SSH usurname: usuario do pi-star. (pi-star)
* -> SSH password: senha do pi-star.
* -> SSH port: 22

![r2](https://user-images.githubusercontent.com/40077152/112875565-ba4e7780-909a-11eb-9c62-dea9d55db767.jpeg)


# RF + (App 'SSH button' ou terminal shell):

* Caso queira selecionar os DG-IDs via rádio faz-se necessário o envio de ***"sete digitos"*** como ***"contato privado"*** para o pi-star aceitar o comandos... sendo os cinco primeiros uma sequência de numeros "8" e os dois últimos números a identificação do DG-ID, salvo os comandos especiais, "reset" e "disconnect". Uma vez aceito o comando pelo pi-star, use o "ID" do servidor escolhido nas configurações do pi-star. Exemplo: "YSC724" Talkgroup TG72401. Se estiver usando ***DMRGateway acrescente*** o número 70 antes do "ID" do servidor: 70+72401 (7072401). Caso queira mudar o TG de saída e não usar o ID do servidor conexão uso o comando: ***sudo out TG (ex: sudo out 10) - TG10 Rx e Tx. Para retornar (sudo out reset). ATENÇÃO: cuidado para não atribuir TG que já esteja em uso e provocar algum conflito! Uso com cuidado!***

* ***-> Contato privado:  88888+(DG-ID)***

* 8888802 (Link dg-id 02) 
* 8888872 (Link dg-id 72)
* 8888896 (Link dg-id 96)  
 
* ***Para que o pi-star identifique corretamente o comando mantenha o ptt pressionado no mínimo 3seg.***

* Conselho: ***Slot 1 para selecionar DG-ID e Slot 2 para QSO(s).***

# Comandos especiais: app 'SSH button' ou terminal shell.

* Ex: 4444400    (Disconnect)
* Ex: 5555500    (Reset: retorna as configurações definidas pelo usuário em 'Expert, YSF GW, Options' )

# YSF GW
* Para dg-id(s) estático(s) declare os dg-id(s) no arquivo de configuração no pi-star.
* 'Configuração' + 'Expert' + 'YSF GW' e no campo 'Options' declare os dg-id(s).

![Options](https://user-images.githubusercontent.com/40077152/112755822-cbbf5300-8fb8-11eb-8600-a852f1b1a61f.png)

# ***ON/OFF Redes Digitais - UPDATE 30/04/2021 - (Reformulado)***
* Menu opção 1 - Script C4FM - V2.4
* -> * Opção de ativar e desativar as "redes digitais" (Network 1-3, xlx e dmr2ysf) via rádio ou celular *
* -> * Network 1: Brandmeister 
* -> * Network 2: IPSC2
* -> * Network 3: Cross-mode (DMR2YSF)
* -> * Função que só se aplica em DMRGateway *

***(Celular - 'SSH button' ou terminal shell)***

* sudo network reset on     (ativa todas as rede  network)
* sudo network reset off    (desativa todas as rede  network)

* sudo network 1 on         (ativa Network 1)
* sudo network 1 off        (desativa Network 1)

* sudo network 2 on         (ativa Network 2)
* sudo network 2 off        (desativa Network 2)

* sudo network 3 on         (ativa Network 3)
* sudo network 3 off        (desativa Network 3)

* sudo network xlx on       (ativa XLX)
* sudo network xlx off      (desativa XLX)

* sudo network dmr2ysf on   (ativa dmr2ysf)
* sudo network dmr2ysf off  (desativa dmr2ysf)

***(RF - Rádio)***
* Para ativar ou desativas as redes, envie uma portatora de 3seg como contato privado "CP": 44444+(comando) / Total de 7 digitos.

* CP: 4444400 = (desativa todas as redes)
* CP: 4444401 = (ativa todas as redes)

* CP: 4444402 = (desativa rede xlx)
* CP: 4444403 = (ativa rede xlx)

* CP: 4444404 = (desativa network 1)
* CP: 4444405 = (ativa network 1)

* CP: 4444406 = (desativa network 2)
* CP: 4444407 = (ativa network 2)

* CP: 4444408 = (desativa network 3)
* CP: 4444409 = (ativa network 3)

* CP: 4444416 = (desativa cross dmr2ysf)
* CP: 4444417 = (ativa cross dmr2ysf)

***Obs: Normalmente as redes no pi-star em DMRGateway são organizadas da seguinte forma: "Network 1=BM", "Network 2=IPSC2" e "Network 3=cros-over/DMR2YSF"***

# ***UPDATE (10/04/2021)***
* Menu opção 1 - Script C4FM - V2.4
* -> * Foi adicionado uma função que declara DG-ID(S) estático(s), standby e seleção de servidores por ID.
* -> * Essas opções só funcinam em servidores YCS com suporte a dg-id.
* -> * Para executar os comandos use o app 'SSH button' ou terminal shell.

* -> * Para seleção estática de algum dg-id use o caractere especial "estrela (*)" seguido do dg-id.
*  Exemplo(s): 
*  dg-id: 72 ( sudo c4fm  *72 )
*  dg-id(s): 72,96,97,24 ( sudo c4fm  *72,96,97,24 )

![ESTATICO](https://user-images.githubusercontent.com/40077152/114287077-7e23fb00-9a3a-11eb-9ed6-c1c63c0962c2.png)

* -> * No modo standby as transmiões são mutadas e o servidor fica aguardando alguma portadora para ser ativo e por tempo determinado.
* -> * Para ativar o modo standby use o símbolo especial "arroba (@)"
*  Exemplo: ( sudo c4fm  @ )

![Estatico-3](https://user-images.githubusercontent.com/40077152/114287087-8d0aad80-9a3a-11eb-9134-5c2c7d15a3ea.png)
![Estatico-2](https://user-images.githubusercontent.com/40077152/114287088-9136cb00-9a3a-11eb-8487-97cfb8acc735.png)


# Conectando servidores YSF ('SSH button' ou terminal shell):

***(sudo ysf + ID)***

* Ex: sudo ysf 56691
* Ex: sudo ysf 90558

* Ex: sudo ysf reset
* Ex: sudo ysf off

# Ativando ou desativando os modos digitais do pi-star (app 'SSH button' ou terminal "shell"):
***(sudo modo + lig/desl)***

* Ex: sudo dmr lig (ON)
* Ex: sudo dmr desl (OFF)

* Ex: sudo d-star lig (ON)
* Ex: sudo d-star desl (OFF)

* Ex: sudo ysf lig (ON)
* Ex: sudo ysf desl (on)
* Ex: sudo ysf reset (default)

***Ativar e desativar "modos digitais" via rádio (RF).***

* DMR OFF   (3333300) ***(Atenção: o uso desta opção exige a ativaçao manual do modo, seja pelo terminal ou por aplicativo 'app')***
* DMR ON    (3333301)

* DSTAR OFF (3333302)
* DSTAR ON  (3333303)

* YSF OFF   (3333304)
* YSF ON    (3333305)

* NXDN OFF  (3333306)
* NXDN ON   (3333307)

* P25 OFF   (3333308)
* P25 ON    (3333309)

# PATCH DMRGateway (Reescrita de TGs):
* Opção 2 - Script C4FM - V2.4
*** *Para uso de servidores DMR com modo 'crossover DMR2YSF' faz-se necessario o uso do DMRGateway, configurado e ativo. Já o pi-star com a rede ipsc2, ativa e em dmrgateway, direciona seu fluxo para um único TG (TG 8) que limita o uso de todos os TGs da rede. Pensando nisso que o 'script c4fm' disponibiliza um patch que faz a reescrita de TGs ipsc2 possibilitando o uso de todos os Tgs e demais servidores DMR.*** 

***-> Obs: *Após aplicar o patch no seu pi-star as configuraçoes de dmrgateway seram reconfiguradas.***
***-> * Ao término de tudo configure o dmrgateway com suas configuraçoes pessoais.***

***(7 Digitos: 20+TG)***

* Ex: TG 724 -> TG 2000724   (Tx/Rx)
* Ex: TG 72431 -> TG 2072431 (Tx/Rx)

* Também é possivel a reescrita dos TGs manualmente, para isso, desabilite as linhas de comando existentes (TGRewrite e PCRewrite) e adicione novos comandos ao arquivo de configuração do DMRGateway na função '[DMR Network 2]'

***'Configuração' + 'Expert' + Full edit: 'DMR GW'***

* #TGRewrite0=2,8,2,9,1
* #TGRewrite1=2,9990,2,9990,1
* #PCRewrite0=2,84000,2,4000,1001

* TGRewrite0=1,2000001,1,1,999999
* TGRewrite1=2,2000001,2,1,999999
* PCRewrite0=1,2000001,1,1,999999
* PCRewrite1=2,2000001,2,1,999999

![ipsc2_gw](https://user-images.githubusercontent.com/40077152/112769622-6e4af680-8ff8-11eb-87ce-128ffa206135.png)

# DMR2YSF + C4FM:
**** Neste modo o dmr2ysf só aceita conexões de servidores c4fm vetando os demais servidores digitais.***

* Ex: TG 72401 -> TG 72401 (Tx/Rx)
* Ex: TG 22201 -> TG 22201 (Tx/Rx)


![72401](https://user-images.githubusercontent.com/40077152/112757078-800fa800-8fbe-11eb-9ba1-270338caa0c0.png)


# DMR2YSF + DMRGateway:

***(7 Digitos: 70+'ID server')***

* Ex: TG 72401 -> TG 7072401 (Tx/Rx)
* Ex: TG 22201 -> TG 7022201 (Tx/Rx)

![7072401](https://user-images.githubusercontent.com/40077152/112756338-15a93880-8fbb-11eb-88c5-cc72d38b9cac.png)

# Instalação: 
* Use o 'ssh do pi-star' ou 'putty'.

#  rpi-rw
#  git clone https://github.com/pu4ron/c4fm.git
#  cd c4fm
#  sudo chmod 755 install
#  sudo chmod +x install
#  sudo ./install

#  sudo reboot
