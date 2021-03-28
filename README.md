# Script C4FM V2.1

***Nota: O presente script tem um conjunto de ferramentas cuja a função é ativar, automatizar e possibilitar o uso de dg-id(s) por equipamentos DMR em crossover (DMR2YSF) no pi-star e foi aproveitado recursos existentes para controle dos dg-id(s) via rádio e por aplicativo (app)... e foi pensando nas possibilidades do pi-star que outras aplicações foram adicionadas para ajudar o usuário em outras modalidades digitais.***

# Importante: 

* -> 1º update. Não continue sem atualizar (UPDATE).
* -> 1.1 - Ative "DMR2YSF" no pi-star.
* -> 1.2 - Selecione o servidor com suporte DG-ID.
* -> 1.3 - Backup do seu pi-star.
* -> 1.4 - Ative o ssh no seu pi-star.

* Lembre-se que o script foi baseado na versão oficial do pi-star v4.1.4
* O servidor de base e referência foi "YSF72401-BR-C4FM-Brasil-YCS724" (default). Outros servidores podem ser usados pelo usuário.
* Suporte a servidores YSF, mas sem suporte a dg-id.
* Painel: http://ycs724.amrase.org.br/ycs/

* Para uso via celular instale o app ***(SSH button)*** que irá criar botões e executar os comandos solicitados. os mesmos comando podem ser executados pelo terminal do pi-star.

# (App 'SSH button' ou modo terminal "shell" do pi-star)::

* -> Label: nome do comando ou DG-ID.
* -> Command: comando a ser executado. => sudo c4fm + (DG-ID)  / sempre dois digitos: 01,02,72,96 etc...  
* Ex: sudo c4fm 72          # dg-id 72
* Ex: sudo c4fm off         # disconnect 
* Ex: sudo c4fm reset       # reset: retorna as configurações definidas pelo usuário.

* -> SSH hostname: ip do raspberry.
* -> SSH usurname: usuario do pi-star. (pi-star)
* -> SSH password: senha do pi-star.
* -> SSH port: 22

# RF + (App 'SSH button' ou modo terminal "shell" do pi-star)::

* Já para uso via rádio faz-se necessário o envio de ***"sete digitos"*** como ***"contato privado"***, sendo os cinco primeiros uma sequência de numeros "8" e os dois últimos números a identificação do DG-ID, salvo os comandos especiais, "reset" e "disconnect". Uma vez aceito o comando pelo pi-star, use o "ID" do servidor escolhido nas configurações do pi-star. Exemplo: "YSC724" Talkgroup TG72401. Se estiver usando ***DMRGateway acrescente*** o número 70 antes do "ID" do servidor: 70+72401 (7072401). Caso queira mudar o TG de saída e não usar o ID do servidor conexão uso o comando: ***sudo out TG (ex: sudo out 10) - TG10 Rx e Tx. Para retornar (sudo out reset). ATENÇÃO: cuidado para não atribuir TG que já esteja em uso e provocar algum conflito! Uso com cuidado!***

* ***-> Contato privado:  88888+(DG-ID)***
* Exemplos:
* Link dg-id 02 (8888802)
* Link dg-id 72 (8888872) 
* Link dg-id 96 (8888896)    
* ***Para que o pi-star identifique corretamente o comando mantenha o ptt pressionado por no mínimo 3seg.***

# Sugestão:
* Use slot 1 para selecionar DG-ID e Slot 2 para QSO(s).

# Comandos especiais (App 'SSH button' ou modo terminal "shell" do pi-star):
* Ex: 4444400    # Disconnect
* Ex: 5555500    # Reset: retorna as configurações definidas pelo usuário.

# Servidores YSF (App SSH button ou modo terminal "shell" do pi-star):
* ***(sudo ysf + ID)***
* 
* Ex: sudo ysf 56691
* Ex: sudo ysf 90558

* Ex: sudo ysf reset
* Ex: sudo ysf off

# Ativar e desligar modos digitais (App 'SSH button' ou modo terminal "shell" do pi-star):
***(sudo modo + Fn)***

*Ex: sudo dmr Lig (ON)
*Ex: sudo dmr Desl (OFF)

*Ex: sudo d-star Lig (ON)
*Ex: sudo d-star Desl (OFF)

*Ex: sudo ysf Lig (ON)
*Ex: sudo ysf Desl (on)




# Instalação: 
* Use o ssh do pi-star.

#  rpi-rw
#  git clone https://github.com/pu4ron/c4fm.git
#  cd c4fm
#  sudo chmod 755 install
#  sudo chmod +x install
#  sudo ./install

#  sudo reboot


