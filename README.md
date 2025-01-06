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

SERVIDOR PROXMOX:
- CPU: i5-3330 
- RAM: 8GB RAM DDR3 1333 MHz
- FUENTE 450W 80 PLUS BRONZE
- DISCOS: 1 HDD 1TB, 2 HDD 500GB, 1 HDD 160GB
- TARGETA DE RED: 1 TARGETA DE RED EXTRA 1 GBPS
No es un servidor muy potente pero actualmente cubre las necessidades a nivel personal. 

Actualmente en mi hipervisor, estoy virtualizando 1 maquina virtual y 3 contenedores. La maquina virtual es un TrueNAS, donde tengo un passtrought de 3 discos fisicos, 1 para el s.o de 160GB y dos de 500GB que forman un RAID ESPEJO, para tener un poco de redundancia. Ademas en los procesadores, utilitzo el tipo "Host", para que utilitze los nucelos e hilos directamente de la CPU. 

## UPDATES
OBVIAMENTE TENGO PENSADO HACER UPDATES

