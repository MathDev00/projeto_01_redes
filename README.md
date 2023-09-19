*Documentação - Projeto de Administração de Redes usando Vagrant com 3 VMs*

1. Introdução

O projeto consistiu em criar três máquinas virtuais, com intuito de oferecer serviços específicos

| Nome da VM  | Descrição |
| ------------- | ------------- |
|  VM I -> Servidor Web (privado)  | Oferece serviços de hospedagens de sistemas web de forma segura. Criação de ambientes de desenvolvimento de forma rápida.  |
| VM II -> Servidor de Banco de Dados (Privado)  | Oferece serviços de armazenamento e compatilhamento do banco de dados da aplicação.  |
| VM III ->  Gateway (Privado DHCP e Pública) | Facilita comunicação entre dispositivos. Fornece segurança para controle de trafego na internet. |

   
2. Execução

Requisitos

| Nome  | Versão |
| ------------- | ------------- |
| Sistema Operacional  | Linux Mint 21.2 |
| Intereface de virtualização  | Vagrant 2.2.19  |
| Provedor  |  VirtualBox Versão 6.1.38 para Ubuntu |

Comandos executados para geração da máquina: terminal


| Ordem | Comandos | Descrição|
| ------------- | ------------- | ------------- |
| 1   | vagrant init    | Criação do Vagrantfile. Codificação das máquinas virtuais    |
| 2     | vagrant up      | Geração da rede de computadores com Vagrantfile     |



   
3. Testes e conclusão

| Ordem | VM | Descrição|
| ------------- | ------------- | ------------- |
| 1   | VM1    | Teste do synced_folder, checagem de compartilhamento das pastas, por meio da navegação das pastas e observação de hospedagem de sites. Teste de instalação do Apache, com comandos Linux na VM em execução. Teste do ping de comunicação entre as máquinas de mesma rede, com endereço de rede 192.168.56.1|
| 2     | VM2     | Teste de ping e instação do Mysql     |
| 3     | VM3    | Teste de configuração da rede pública. Comunicação com outras VM's e provimento de internet para as demais redes. Teste de mascaramento das redes |


