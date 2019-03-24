# virusystem_infra
virusystem Infra repository

Как можно подключиться в одну строку.
ssh -A otus-homework@104.199.9.247 ssh -t -t otus-homework@10.132.0.3

Более праильный путь. создать в каталоге .ssh файл config со следующим содержимым
Host bastion
  User otus-homework
  HostName 104.199.9.247
  IdentityFile ~/.ssh/id_rsa

Host someinternalhost
  Hostname 10.132.0.3
  User otus-homework
  IdentityFile ~/.ssh/id_rsa
  ProxyJump bastion
  
теперь для подключения достаточно написать ssh someinternalhost
