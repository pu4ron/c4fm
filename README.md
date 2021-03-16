# c4fm
* O presente script tem a função de ativar o modo DG-ID em DMR2YSF no pi-star e de adicionar e possibilitar a função de controle remota para os DG-ID(s) nos rádios DMR e dando suporte para controle por aplicativo via celular.

* Antes de qualquer procedimento faça um backup e atualize seu pi-star. 
* Vale lembrar que o script foi baseado na versão oficial v4.1.4 e 4.1.3 na EA7EE/Espanhol.

* Para uso em celular instale o app (SSH button) que irá criar botões e executar os comandos.
* Ative no seu pi-star o acesso ao ssh em configurações e mude a opção de ssh para public e click em aplicar.

-> Label: identificação do comando ou DG-ID
-> Command: comando a ser executado. sudo c4fm + (DG-ID)  
Ex: sudo c4fm 72
-> SSH hostname: ip do raspberry pi
-> SSH usurname: usuario do pi-star. (pi-star)
-> SSH password: senha do pi-star
-> SSH port: 22


