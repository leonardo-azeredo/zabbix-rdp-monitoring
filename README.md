# zabbix-rdp-monitoring
Monitorando acessos RDP em máquinas Windows com Zabbix


É disponibilizado nesse repositório: o Agent 2 do Zabbix "zabbix_agent2-6.2.1-windows-amd64-openssl.msi", o Script Powershell "rdp.terminal.server.ps1", o diretório com o módulo do powershell "PSTerminalServices" e o .msi "rdp.terminal.server.msi"


1° Passo: Instale o .msi "rdp.terminal.server.msi" na máquina a ser monitorada

![image](https://user-images.githubusercontent.com/114172861/195118697-b8c39d71-d467-4fa6-9ba0-c25ad9874f8e.png)




2° Passo: Copie o diretório "PSTerminalServices" desse repo e cole no seguinte caminho da máquina a ser monitorada C:\Windows\System32\WindowsPowerShell\v1.0\Modules\

![image](https://user-images.githubusercontent.com/114172861/195118853-b01478be-9d46-4e9d-9b49-93fb9c96ae7b.png)



3° Passo: Crie um diretório e cole o script "rdp.terminal.server.ps1" Será necessário apontar o script powershell dentro do .conf do agent, faça isso colando a seguinte linha no .conf "UserParameter=rdp.terminal.server[*],powershell.exe -noprofile -executionpolicy bypass -File (CAMINHO DO ARQUIVO rdp.terminal.server.ps1)  $1"


4° Passo: Reinicie o Agent e importe o .xml "sessoes_RDP_ativas_by_leonardo-azerdo.xml" para o seu zabbix

![image](https://user-images.githubusercontent.com/114172861/195115175-d83c450d-5e60-4706-a167-d52edddf3736.png)

Pronto, você ja pode sair criando os seus hosts e adicionando o template!.
