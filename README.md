# c4fm
* O presente script tem a função de ativar e possibilitar o modo DG-ID em DMR2YSF na distribuição oficial do pi-star, bem como ativando a função de controle remota por rádios DMR e ofertando suporte para controle por aplicativos, app de celular. Possibilitando os equipamentos DMR uso e controle dos DG-ID do C4FM. Suporte também a distribuição EA7EE/Espanhol do pi-star.

* Antes de qualquer procedimento faça um backup e atualize seu pi-star. 
* Vale lembrar que o script foi baseado na versão oficial v4.1.4 e 4.1.3 EA7EE/Espanhol.
* O servidor usado para base do projeto foi o "YSF72401-BR-C4FM-Brasil-YSC724" que deve ser ativado no seu pi-star para uso do script.
* Painel: http://ycs724.amrase.org.br/ycs/

* Para uso em celular instale o app (SSH button) que irá criar botões e executar os comandos.
* Ative no seu pi-star o acesso ao ssh em "configurações" e mude a opção de ssh para "public" e click em "aplicar".

-> Label: nome do comando ou DG-ID.
-> Command: comando a ser executado. => sudo c4fm + (DG-ID)  / sempre dois digitos: 01,02,72,96 etc...  
Ex: sudo c4fm 72          # dg-id 72
Ex: sudo c4fm off         # disconnect 
Ex: sudo c4fm reset       # reset: retorna as configurações definidas pelo usuário.

-> SSH hostname: ip do raspberry.
-> SSH usurname: usuario do pi-star. (pi-star)
-> SSH password: senha do pi-star.
-> SSH port: 22


* Já para uso via rádio faz-se necessário o envio de sete digitos como contato privado, sendo os cinco primeiros uma sequência de numeros "8" e os dois últimos números a identificação dos DG-IDs, salvo os comandos especiais, reset e disconnect. Uma vez aceito o comando pelo pi-star, uso o ID do servidor "YSC724" como Talkgroup TG72401. Se estiver usando DMRGateway: 7072401.

->Contato privado:  88888+(DG-ID)
Ex: 
Link dg-id 02 (8888802)
Link dg-id 72 (8888872) 
Link dg-id 96 (8888896)    
Para que o pi-star identifique corretamente o comando mantenha o ptt pressionado por no mínimo 3seg.

* Comandos especiais:
Ex: 4444400    # disconnect
Ex: 5555500    # reset: retorna as configurações definidas pelo usuário.


# Instalação: 
* Use o ssh do pi-star.

#  rpi-rw
#  git clone https://github.com/pu4ron/c4fm.git
#  cd c4fm
#  sudo chmod 777 install
#  sudo chmod +X install
#  sudo ./install

#  sudo reboot


