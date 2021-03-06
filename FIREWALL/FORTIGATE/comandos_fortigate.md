## COMANDOS FW FORTIGATE


# TROUBLESHOOTING   
 #### ANÁLISE DE TRÁFEGO DE REDE   
   	diagnose sys session filter src 192.168.3.68
    diagnose sys session filter dst 192.168.3.68
    diagnose sys session clear
    diagnose sniffer packet any 'host 192.168.3.68' 
    diagnose sniffer packet any 'host 192.168.3.68 and icmp'
 #### TCP RST packet on session timeout

    config firewall policy
    edit <ID>
    set timeout-send-rst enable
    
Ping    

    execute ping-options source 10.0.1.1 
    execute ping 172.31.11.180

Tracert   
 
    execute traceroute-options source 10.0.11.1
    execute traceroute 192.168.1.180

Acessar Cluster Slave         

    Verificar o ID do Cluster  
    get system ha status    

    Acessar o Cluster    
    execute ha manage ID_CLUSTER      

Balance entre os HA    

    config system ha
    set load-balance-all enable

Criar usuário sem a senha    

    config system admin
    edit ronaldo.augusto
    set accprofile super_admin
    end

Verificar informações de Memoria, CPU e Disco    

    get hardware status
    diagnose sys top 1 45
    diagnose sys top-summary
    diagnose sys top-all
    get system performance status   
#### CRIAR ROTA POR SSH     

    config router static
    edit 12
    set dst 182.168.224.0 255.255.255.0
    set gateway 172.16.1.100
    set device "lan"
    set comment "ACESSO FW-DNAT"
    next   
    end   
#### PRIORIDADE VPN NA SDWAN 

    config system virtual-wan-link 
    config members 
    edit (numero da interface que esta na sdwan)
    set priority 10 
    end    

    OBS/: só precisará mexer se for criado uma nova VPN SDWAN

#### CONFIGURAR AUTENTICAÇÃO FSSO EM POLICY   

    config firewall policy   
   	edit  32 (Nº da Politica)
   	set ntlm enable 
	set fsso enable 
	set fsso-agent-for-ntlm AD 
 
#### Lista todos hosts do DHCP lease
    execute dhcp lease-list  
#### Especifique por porta  
    execute dhcp lease-list port1
#### Use o seguinte comando para limpar a concessão do cliente com o endereço IP
    execute dhcp lease-clear 192.168.1.5

#### Para limpar TODAS as concessões, use
    execute dhcp lease-clear all
#### O seguinte comando irá retornar com uma lista em branco ou menor
    execute dhcp lease-list
#### Para listar os IPS em V6, use o comando dhcp6
    execute dhcp6 lease-list