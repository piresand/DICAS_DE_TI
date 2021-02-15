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
#### VER STATUS DO BANCO DE DADOS   
    [root@ipbx backup]# /etc/rc.d/init.d/postgresql status
#### STARTAR O SERVICO DO BANCO DE DADOS   
    [root@ipbx backup]# /etc/rc.d/init.d/postgresql start
#### VER ARQUIVOS DE ROTINA DO LINUX   
    [root@ipbx scripts]# cat /etc/crontab
#### EDITAR ARQUIVOS DE ROTINAS DO LINUX   
    [root@ipbx scripts]# nano -w /etc/crontab
#### ACESSO DA PASTA SCRIPT   
    [root@ipbx ~]# cd /hdaux/utilitarios/scripts/
#### RODAR COMANDO PARA UTILIZAR O SCRIPT NOVO   
    [root@ipbx scripts]# sh /hdaux/utilitarios/scripts/backup.sh
#### VER ARQUIVO BACKUP.SH   
    [root@ipbx scripts]# cat backup.sh
#### VER TAMANHO DO DIRETORIO OU ARQUIVO   
    [root@ipbx scripts]# du -h
#### VER ARMAZENAMENTO DO DISCO   
    [root@ipbx scripts]# df -h
#### ADICIONAR ROTA 
    nano -w /etc/sysconfig/network-scripts/route-eth2

    102.14.10.0/18 via 180.16.70.50
    100.45.10.0/18 via 180.16.70.50
    189.113.14.36/32 via 180.16.70.50
##### ADICIONAR ROTA TEMPORÁRIA
    route add -net 100.64.0.0/18 gw 180.16.70.50
    route add -net 100.64.64.0/18 gw 180.16.70.50

*** NECESSÁRIO ALTERAR OS IPS CONFORME TOPOLOGIA ***