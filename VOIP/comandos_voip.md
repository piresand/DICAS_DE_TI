# COMANDOS IPBX
#### ACESSAR O DISCO HD   
    [root@ipbx ~]# cd /hdaux/
#### LISTAR OS ARQUIVOS DA PASTA HDAUX   
    [root@ipbx hdaux]# ls
    atualizacao  backup  channel_4.3_008_legacy_x86-64.sh  downloads  restore  utilitarios
#### ACESSAR A PASTA BACKUP   
    [root@ipbx hdaux]# cd backup/
    [root@ipbx backup]# ls
#### REMOVER ARQUIVOS    
    [root@ipbx backup]# rm -rf 2019*
    [root@ipbx backup]# rm -rf  backup-2019*
#### LIMPAR MEMÓRIA DO IPBX      
    [root@ipbx ~]# history | grep sync  
    sync; echo 1 > /proc/sys/vm/drop_caches   
#### VER STATUS DO BANCO DE DADOS   
    [root@ipbx backup]# /etc/rc.d/init.d/postgresql status
#### INICIAR O SERVICO DO BANCO DE DADOS   
    [root@ipbx backup]# /etc/rc.d/init.d/postgresql start
#### VER ARQUIVOS DE ROTINA DO LINUX   
    [root@ipbx scripts]# cat /etc/crontab
#### EDITAR ARQUIVOS DE ROTINAS DO LINUX   
    [root@ipbx scripts]# nano -w /etc/crontab
#### ACESSO DA PASTA SCRIPT   
    [root@ipbx ~]# cd /hdaux/utilitarios/scripts/
#### RODAR COMANDO PARA UTILIZAR O SCRIPT NOVO   
    [root@ipbx scripts]# sh /hdaux/utilitarios/scripts/backup.sh
#### VER ARQUIVO BACKUP SH   
    [root@ipbx scripts]# cat backup.sh
#### VER TAMANHO DO DIRETORIO OU ARQUIVO   
    [root@ipbx scripts]# du -h
#### VER ARMAZENAMENTO DO DISCO   
    [root@ipbx scripts]# df -h
#### LISTAR ARQUIVOS COM SIZE DE 20M    
    [root@ipbx monitor]# find -size +20M   
##### VER TAMANHO DO AUDIO    
    [root@ipbx monitor]# du -h ./00000-1036642039-1608580417.1185033.WAV     
    2.5G    ./00000-1036642039-1608580417.1185033.WAV    
##### LISTAR INFO DE TODAS AS MEMÓRIAS  
    [root@ipbx ~]# cat /proc/meminfo
#### LISTAR PROCESSOS EM USO, MEMÓRIA, UPTIME E CPU        
    [root@ipbx ~]# top      
#### ABRIR E EDITAR O SERVILÇO CONTRAB    
    ~ # nano  /etc/crontab     
#### CRIAR ROTINA DE LOGS NO CRONTAB COM TCPDUMP - DURAÇÃO DE 4Hrs    
    #log interfones    
    30 17 * * * root tcpdump -G 14400 -W 1 -s 3000 -w /home/captura_ramais.pcapng -i eth1    
#### CRIAR ROTINA DE LOGS NO CRONTAB COM TCPDUMP - DURAÇÃO DE 24Hrs    
    #log interfones    
    00 11 * * * root tcpdump -G 86400 -W 1 -s 3000 -w /home/captura_ramais.pcapng -i eth1    
#### APÓS CRIAR ROTINA, NECESSÁRIO REINICIAR O SERVICE DO CONTRAB
    [root@ipbx ~]# service crond restart
 #### SNIFFER COM TCPDUMP      
    [root@ipbx ~]# sudo tcpdump -i eth0 port 5060 -vv    
    [root@ipbx ~]# sudo tcpdump -i eth0 port 5060 
    [root@ipbx ~]# sudo tcpdump -i eth0 dst 100.64.5.183 -vvv
#### ADICIONAR ROTA 
    nano -w /etc/sysconfig/network-scripts/route-eth2

    102.14.10.0/18 via 180.16.70.50

    *** NECESSÁRIO ALTERAR OS IPS CONFORME TOPOLOGIA ***
#### ADICIONAR ROTA TEMPORÁRIA
    route add -net 100.60.0.0/18 gw 190.16.7.50

    *** NECESSÁRIO ALTERAR OS IPS CONFORME TOPOLOGIA ***
# Comandos Básicos Asterisk (SSH)
#### Mostra as conexões SIP do asterisk – Ramais e troncos SIP   
    sip show peers
#### Mostra o ramal com detalhes e se está autenticado ou não   
     sip show peer + ramal 
#### Mostra os ramais e troncos que estão em ligação e presos   
    core show channels verbose
#### Comando serve para derrubar o ramal que esta travado como se estive-se em ligação a horas   
    soft hangup SIP/Ramal
#### Comando serve para monitor um único ramal desejado
    rasterisk -vvv | grep "ramal"
#### Mostra o status dos agentes (este comando é apenas quando os usuários Logan na central)
    show agents online
