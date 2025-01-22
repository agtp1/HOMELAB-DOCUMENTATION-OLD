# SIGO EN PROCESO DE DOCUMENTACION DE MI HOMELAB

## ELEMENTOS DE RED
ROUTER:
- [Microtik hAP ac^2]([url](https://www.pccomponentes.com/mikrotik-hap-ac2-punto-de-acceso1167mbps-dual-band-poe?utm_source=366479&utm_medium=afi&utm_campaign=es-go.kelkoogroup.net&sv1=affiliate&sv_campaign_id=366479&awc=20981_1736207023_47a5b89131152021a64a39caa9ae412f&utm_term=deeplink&utm_content=62A001JGZ01FAS3PDVMEC6KPH2GEST))
  
![image](https://github.com/user-attachments/assets/7798fc39-5f98-4b87-86a9-4a8ef039f4ff)

SWITCH PRINCIPAL
- [Mikrotik RB260GS ]([url](https://www.pccomponentes.com/mikrotik-rb260gs-switch-5-puertos-gigabit-1-sfp))
  
![image](https://github.com/user-attachments/assets/53819aa6-65ea-4c46-bd8c-631e6921c3e4)

SWITCH CLIENTES:
- [D-LINK  DGS-108]([url](https://www.pccomponentes.com/d-link-dgs-108-switch-8-puertos-10-100-1000mbps))
  
![image](https://github.com/user-attachments/assets/c9d015b1-5afd-495b-b259-84c7b7ed6fb8)

CLUSTER PROXMOX:
NODE 1
- MINI PC Teclast n10
- 6GB ram SODIMM DDR4
- CPU Celeron N4000 2 nucleos 2 hilos 2,6 GHz
- Disco Duro Externo SSD KINGSTON 240 SATA

NODE 2
- CPU: i5-3330 
- RAM: 8GB RAM DDR3 1333 MHz
- FUENTE 450W 80 PLUS BRONZE
- DISCOS: 1 HDD 1TB, 2 HDD 500GB, 1 HDD 160GB
- TARGETA DE RED: 1 TARGETA DE RED EXTRA 1 GBPS
No es un servidor muy potente pero actualmente cubre las necessidades a nivel personal. 

FUNCIONES NODO 1:
En el nodo 1 simplemente estoy corriendo 4 contenedores:
- ADBLOCKER: Adguard
- DASHBOARD: Homarr
- PROXY: Nginx Proxy Manager
- GESTOR PASSWORDS: VaultWarden
CONSUMOS NODO 1:
Aunque parezcan pocos recursos, la CPU Y la RAM, son más que suficientes para mantener activos y en correcto funcionamiento los servicios que necesito.
![image](https://github.com/user-attachments/assets/6725ce7b-9dec-42f6-bf01-45e6e5a631a1)
![image](https://github.com/user-attachments/assets/bd602392-47f6-4571-825a-dd0ed2bad044)


FUNCIONES NODO 2:
En el nodo 2 actualmente solo tengo corriendo un TrueNAS, donde tengo varias carpetas compartidas vía SAMBA, también gestiono las COPIAS DE SEGURIDAD, tanto de PROXMOX, como del propio TrueNAS. En este TrueNAS, he realizado un PASSTROUGHT, de 3 discos físicos. 1 de 160GB donde simplemente está instalado el s.o, y 2 de 500GB cada uno que forman un RAID1. Dentro de TrueNAS, tengo corriendo un pequeño servidor de vídeo, concretamente Jellyfin. Donde actualmente tengo algunos capítulos de algunas series que me gustaría ver. Además, los núcleos asignados a esta máquina virtual, están en modo HOST, para que la máquina virtual utilice directamente los núcleos de la CPU. Un espacio de TrueNAS, está dedicado para las copias de seguridad de los contenedores del NODO1, este espacio está compartido mediante NFS, y está asignado al propio PROXMOX.
CONSUMOS NODO 2:
![image](https://github.com/user-attachments/assets/6e920980-fa33-4240-be01-4b6471b62c1b)


![image](https://github.com/user-attachments/assets/5818c098-8522-47f3-91f1-1e8a17752d91)




## UPDATES
OBVIAMENTE TENGO PENSADO HACER UPDATES

