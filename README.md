*Documentação - Projeto de Administração de Redes usando Vagrant com 3 VMs*

1. Introdução

O projeto consistiu em criar uma rede de computadores com os requisitos de serviços abaixo

| N | REQUISITOS |
| ------------- | ------------- |
|  RQ01  | Configure um servidor DHCP no ambiente Linux para atribuir endereços IP automaticamente aos dispositivos na rede. |
| RQ02  |Implante um servidor DNS para resolver nomes de domínio dentro da rede e configurar registros DNS como A, CNAME, MX  |
| RQ03| Configure e hospede um servidor web Apache ou Nginx para fornecer serviços de hospedagem de sites internos|
| RQ04| Implemente um servidor FTP (por exemplo, vsftpd) para permitir a transferência de arquivos na rede |
| RQ05| Configure um servidor NFS para compartilhar diretórios e arquivos entre máquinas na rede.|


   
2. Execução

Requisitos

| Nome  | Versão |
| ------------- | ------------- |
| Sistema Operacional  | Linux Mint 21.2 |
| Intereface de virtualização  | Vagrant 2.2.19  |
| Provedor  |  VirtualBox Versão 6.1.38 para Ubuntu |
| Serviços  |  Docker 24.0.5 |


Comandos executados para geração da máquina: terminal


| Ordem | Comandos | Descrição|
| ------------- | ------------- | ------------- |
| 1   | vagrant init    | Criação do Vagrantfile. Codificação das máquinas virtuais    |
| 2     | vagrant up      | Geração da rede de computadores com Vagrantfile     |

Comandos importantes do Vagrantfile: referência do código em ruby do repositório


| Ordem | Comandos | Descrição|
| ------------- | ------------- | ------------- |
| 1   | vm.box   | Configuração do sistema operacional    |
| 2     | network    | Definição e configuração de rede    |
| 3     |synced_folder    | Compartilhamento de pasta do host para hospedagem de site    |
| 4     |provision   | Uso de comandos da linguagem bash para instalação de pacotes    |
| 5    |ip rout add default via   | Rota da rede para gateway (config)   |
| 6   |sudo iptables e -j MASQURRADE  | RConfiguração do nat para acesso à internet   |



   
3. Testes e conclusão

| Ordem | VM | Descrição|
| ------------- | ------------- | ------------- |
| 1   | VM1    | Teste do synced_folder, checagem de compartilhamento das pastas, por meio da navegação das pastas e observação de hospedagem de sites. Teste de instalação do Apache, com comandos Linux na VM em execução. Teste do ping de comunicação entre as máquinas de mesma rede, com endereço de rede 192.168.56.1|
| 2     | VM2     | Teste de ping e instação do Mysql     |
| 3     | VM3    | Teste de configuração da rede pública. Comunicação com outras VM's e provimento de internet para as demais redes. Teste de mascaramento das redes |


