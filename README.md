# Script C4FM - V2.2 

***Nota: O 'script c4fm' é um conjunto de ferramentas cuja a função é ativar, automatizar e possibilitar o uso de dg-id(s) por equipamentos DMR usando o modo cross-over (DMR2YSF) do pi-star e foi aproveitado esse e outros recursos que surgem os controles de dg-id(s) por rádio e aplicativo (app).***

# ***NEW UPDATE: BLUEDV-PISTAR 06/04/2021***
* Opção 3 - Script C4FM - V2.2
* Para aqueles que gostam de brincar, divertir e ser feliz que foi adicionado ao conjunto de ferramentas do pi-star suporte para o aplicativo Bluedv.
* Algumas informações são importates: Bluedv só trabalha com um slot (simplex) e obrigatoriamente deve está na mesma rede wifi ou cabeada do pi-star. 
* Estando o bluedv ativo o pi-star fica inativo e o retono normal se dá desligando o bluedv e reiniciando o pi-star/raspberry. 
* Em alguns casos faz-se necessário desabilitar o bluedv na opção 'Setup' e desmarcar 'enable ser2net' e o inverso para ativar.
* Em alguns casos faz-se necessário desabilitar todos os serviços do pi-star, se for seu caso, use o comando (sudo stop) ou use o 'app ssh button' com um botão configurado com o comando.
* Pensamento do dia: "Não queira de graça aquilo que você tem capacidade de obter adquirir!"  D. Mauro, cp.
* Download: https://play.google.com/store/apps/details?id=com.pa7lim.BlueDV&hl=pt_BR&gl=US

![Rx-1](https://user-images.githubusercontent.com/40077152/113786152-f6bf4a80-970e-11eb-8f92-917b0893c799.jpeg)
![Tx-1](https://user-images.githubusercontent.com/40077152/113781542-384bf780-9707-11eb-8368-b9bb31fb2ddf.jpeg)
![Tx-3](https://user-images.githubusercontent.com/40077152/113785767-2883e180-970e-11eb-96dd-028ad51338bf.jpeg)
![2](https://user-images.githubusercontent.com/40077152/113781959-d770ef00-9707-11eb-81ab-99e423e60791.jpeg)
![1](https://user-images.githubusercontent.com/40077152/113781563-426df600-9707-11eb-8267-978ca3fb591b.jpeg)
![3](https://user-images.githubusercontent.com/40077152/113781584-49950400-9707-11eb-9139-5e9c106ef0f0.jpeg)
![4](https://user-images.githubusercontent.com/40077152/113781593-4d288b00-9707-11eb-8cfb-8d52e15ea3a6.jpeg)
![5](https://user-images.githubusercontent.com/40077152/113781608-50bc1200-9707-11eb-96c6-7114e237e999.jpeg)


# ***UPDATE 04/04/2021***
* Opção 1 - Script C4FM - V2.2
* -> * Foi adiconado a opção de ativar e desativar as "redes digitais" (Network 1,2,3,xlx) via rádio ou celular *
* -> * Função que só se aplica em DMRGateway *


***(Celular - 'SSH button' ou terminal shell)***

* sudo net0 reset    (retornas as configutações definidas pelo usuário)
* sudo net0 off      (desativa todas as rede)

* sudo net1 on       (ativa Network 1)
* sudo net1 off      (desativa Network 1)

* sudo net2 on       (ativa Network 2)
* sudo net2 off      (desativa Network 2)

* sudo net3 on       (ativa Network 3)
* sudo net3 off      (desativa Network 3)

* sudo xlx on        (ativa XLX)
* sudo xlx off       (desativa XLX)

***(RF - Rádio)***
* Para ativar ou desativas as redes, envie uma portatora de 3seg como contato privado "CP": 44444+(comando) / Total de 7 digitos.

* CP: 4444400 = (desativa as redes)
* CP: 4444401 = (reset - retorna as configurações do usuário)

* CP: 4444402 = (desativa rede xlx)
* CP: 4444403 = (ativa rede xlx)

* CP: 4444404 = (desativa network 1)
* CP: 4444405 = (ativa network 1)

* CP: 4444406 = (desativa network 2)
* CP: 4444407 = (ativa network 2)

* CP: 4444408 = (desativa network 3)
* CP: 4444409 = (ativa network 3)

***Obs: Normalmente as redes no pi-star em DMRGateway são organizadas da seguinte forma: "Network 1=BM", "Network 2=IPSC2" e "Network 3=cros-over/DMR2YSF"***


# ***UPDATE 03/04/2021***
* Opção de ativar e desativar os "modos digitais" via rádio.

* DMR OFF   (3333300) ***(Atenção: o uso desta opção exige a ativaçao manual do modo, pelo terminal ou por aplicativo 'app')***
* DMR ON    (3333101)

* DSTAR OFF (3333302)
* DSTAR ON  (3333303)

* YSF OFF   (3333304)
* YSF ON    (3333305)

* NXDN OFF  (3333306)
* NXDN ON   (3333307)

* P25 OFF   (3333308)
* P25 ON    (3333309)

# ***UPDATE 01/04/2021***
* Seleção de servidores C4FM via rádio. (***Somente do brasil***)
* Para selecionar, envie uma portatora de 3seg como contato privado: 80+ID do servidor  (7 digitos)

* 8072400 (Brasil-Link)
* 8077777 (Brazilnet)
* 8072401 (C4FM-Brazil)
* 8090558 (PU2LRZ)
* 8095973 (PU4ARR)
* 8056691 (YSF-BRASIL)
* 8001466 (YSF-Minas)
* 8072526 (BRAZIL-724)

* ***Utlilize o 'ID' do servidor que foi selecionado para falar e se estiver usando DMRGateway, adicione o número 70 antes do ID.***
 
# Leia-me: 

* -> 1.0 - Update. Não continue sem atualizar seu pi-star.
* -> 1.1 - Ative "DMR2YSF".
* -> 1.2 - Selecione um servidor com suporte DG-ID.
* -> 1.3 - Faça backup do seu pi-star.
* -> 1.4 - Ative o SSH.

* Script baseado na versão 4.1.4 do pi-star.
* Servidor de referência: "YSF72401-BR-C4FM-Brasil-YCS724" (Default). 
* Outros servidores podem ser utilizados pelo usuário, com ou sem suporte a dg-id.
* Suporte a servidores YSF.
* Painel: http://ycs724.amrase.org.br/ycs/

* Para uso via celular instale o app ***(SSH button)*** que irá criar botões e executar os comandos solicitados... 
* Os mesmos comando podem ser executados no terminal shell do pi-star.

# App 'SSH button':

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

* Já para uso via rádio faz-se necessário o envio de ***"sete digitos"*** como ***"contato privado"***, sendo os cinco primeiros uma sequência de numeros "8" e os dois últimos números a identificação do DG-ID, salvo os comandos especiais, "reset" e "disconnect". Uma vez aceito o comando pelo pi-star, use o "ID" do servidor escolhido nas configurações do pi-star. Exemplo: "YSC724" Talkgroup TG72401. Se estiver usando ***DMRGateway acrescente*** o número 70 antes do "ID" do servidor: 70+72401 (7072401). Caso queira mudar o TG de saída e não usar o ID do servidor conexão uso o comando: ***sudo out TG (ex: sudo out 10) - TG10 Rx e Tx. Para retornar (sudo out reset). ATENÇÃO: cuidado para não atribuir TG que já esteja em uso e provocar algum conflito! Uso com cuidado!***

* ***-> Contato privado:  88888+(DG-ID)***

* 8888802 (Link dg-id 02) 
* 8888872 (Link dg-id 72)
* 8888896 (Link dg-id 96)  
 
* ***Para que o pi-star identifique corretamente o comando mantenha o ptt pressionado por no mínimo 3seg.***

* Conselho: ***Slot 1 para selecionar DG-ID e Slot 2 para QSO(s).***

# Comandos especiais: app 'SSH button' ou terminal shell.

* Ex: 4444400    (Disconnect)
* Ex: 5555500    (Reset: retorna as configurações definidas pelo usuário em 'Expert, YSF GW, Options' )

# YSF GW
* Para dg-id estático declare os dg-id(s) no arquivo de configuração no pi-star.
* 'Configuração' + 'Expert' + 'YSF GW' e no campo 'Options' declare os dg-id(s).

![Options](https://user-images.githubusercontent.com/40077152/112755822-cbbf5300-8fb8-11eb-8600-a852f1b1a61f.png)


# Conectando servidores YSF ('SSH button' ou terminal shell):

***(sudo ysf + ID)***

* Ex: sudo ysf 56691
* Ex: sudo ysf 90558

* Ex: sudo ysf reset
* Ex: sudo ysf off

# Ativando ou desligando os modos digitais do pi-star (app 'SSH button' ou terminal "shell"):
***(sudo modo + lig/desl)***

* Ex: sudo dmr lig (ON)
* Ex: sudo dmr desl (OFF)

* Ex: sudo d-star lig (ON)
* Ex: sudo d-star desl (OFF)

* Ex: sudo ysf lig (ON)
* Ex: sudo ysf desl (on)
* Ex: sudo ysf reset (default)

# PATCH DMRGateway (Reescrita de TGs):
* Opção 2 - Script C4FM - V2.2
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
