# zabbix-rdp-monitoring
Monitorando acessos RDP em máquinas Windows com Zabbix

Será necessário instalar na máquina o msi "rdp.terminal.server.msi", após a instalação será necessário apontar o script Powershell "rdp.terminal.server.ps1" dentro da configuração do Agent do Zabbix, você deverá acessar o .conf do agent e adicionar a seguinte linha "UserParameter=rdp.terminal.server[*],powershell.exe -noprofile -executionpolicy bypass -File <CAMINHO DO ARQUIVO rdp.terminal.server.ps1>  $1".
após isso copie o diretório "PSTerminalServices" desse repositório e cole em C:\Windows\System32\WindowsPowerShell\v1.0\Modules\ 
Importe o .xml "sessoes_RDP_ativas_by_leonardo-azerdo.xml" para o seu zabbix
![image](https://user-images.githubusercontent.com/114172861/195115175-d83c450d-5e60-4706-a167-d52edddf3736.png)
Pronto, você ja pode sair criando os seus hosts e adicionando o template!.
