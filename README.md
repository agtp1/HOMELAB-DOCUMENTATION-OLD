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

DISTRIBUCIÓN RED:
- Salida a internet: Para abrir puerto y salir a internet mantengo el router de mi ISP. Simplemente lo utilizo para tener conectividad a internet.
ROUTER PRINCIPAL:
- Al router le llega 1 cable a la ETH1, que es por donde salimos a internet. Seguidamente, en la ETH5, es mi puerto TRUNK del ROUTER, es decir en este puerto tengo hecha la encapsulación con las vlans para que el SWITCH PRINCIPAL, pueda gestionar y visualizar estas VLANS. También he metido la ETH5, en un BRIDGE, a este BRIDGE. le he asignado una IP y he creado un DHCP, para que el SWITCH PRINCIPAL, reciba una IP.
  
![image](https://github.com/user-attachments/assets/a4b78863-12ed-4e0e-85bd-0d095123d9dc)
![image](https://github.com/user-attachments/assets/5d183738-58ba-40dd-a96e-06ee83921f12)


Las tres VLANS utilizadas en mi red, como he mencionado anteriormente están encapsuladas y asignadas al puerto TRUNK del ROUTER, es decir que cuelgan del ROUTER

![image](https://github.com/user-attachments/assets/dc738316-7a97-4c16-9610-e643ad011b88)


- Servidor VPN WIREGUARD:
  
![image](https://github.com/user-attachments/assets/6573f96c-d043-4222-8d72-f9efe3edcfd1)

- VLANS
  
![image](https://github.com/user-attachments/assets/264cff11-7cf6-4dfb-baa1-eea9d00a5b56)

- ASSIGNACIÓN IPs:
  
![image](https://github.com/user-attachments/assets/75e3e6e6-8bcf-4b9c-b55e-522db6d1c89e)

- SERVIDOR DHCP:
  
![image](https://github.com/user-attachments/assets/c3de47e0-e25c-43f1-8b1b-72654da12fb3)

SWITCH PRINCIPAL:
- El puerto 1 es el puerto TRUNK del SWITCH, es decir esta fisicamente conectado con un cable a mi puerto trunk del router. Es decir que el router se conecta por el puerto 5 y el switch por el puerto 1. Básicamente los puertos trunk ven todas las VLAN. En este caso el puerto 3 y 4 también estan en modo TRUNK, ya que es donde van conectados los dos nodos de proxmox, y me interesa que los dos nodos vean ambas vlans. Y el puerto 1, esta assignado la vlan 30, ya que aquí es donde se conecta la camara de seguridad.
  
![image](https://github.com/user-attachments/assets/5df0c862-8a06-465d-aee2-8e3bccc3616d)
![image](https://github.com/user-attachments/assets/345e2a83-48c4-4513-899b-df8f4d06f2a8)
![image](https://github.com/user-attachments/assets/8d9b50f6-19a2-41df-81e5-f33f88a25fce)



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

![image](https://github.com/user-attachments/assets/79c02160-3f5b-452b-8f16-c599ef1f7d47)

 
- DASHBOARD: Homarr

![image](https://github.com/user-attachments/assets/c1390a65-6dfa-447f-a59b-2eec6679aaf6)


- PROXY: Nginx Proxy Manager

![image](https://github.com/user-attachments/assets/dfd765ed-ce17-42f9-bd99-47e523b37717)


- GESTOR PASSWORDS: VaultWarden

![image](https://github.com/user-attachments/assets/1525570c-bd01-4b54-b7e3-eea283b56343)

  
- MONITORIZACIÓN: UptimeKuma

  ![image](https://github.com/user-attachments/assets/2fe61ea1-fb33-45d2-9d81-056f65bba63d)

  
CONSUMOS NODO 1:
Aunque parezcan pocos recursos, la CPU Y la RAM, son más que suficientes para mantener activos y en correcto funcionamiento los servicios que necesito.

![image](https://github.com/user-attachments/assets/6725ce7b-9dec-42f6-bf01-45e6e5a631a1)
![image](https://github.com/user-attachments/assets/249f0f1b-741d-427a-9981-19cb442aa3ad)



FUNCIONES NODO 2:
En el nodo 2 actualmente solo tengo corriendo un TrueNAS, donde tengo varias carpetas compartidas vía SAMBA, también gestiono las COPIAS DE SEGURIDAD, tanto de PROXMOX, como del propio TrueNAS. En este TrueNAS, he realizado un PASSTROUGHT, de 3 discos físicos. 1 de 160GB donde simplemente está instalado el s.o, y 2 de 500GB cada uno que forman un RAID1. Dentro de TrueNAS, tengo corriendo un pequeño servidor de vídeo, concretamente Jellyfin. Donde actualmente tengo algunos capítulos de algunas series que me gustaría ver. Además, los núcleos asignados a esta máquina virtual, están en modo HOST, para que la máquina virtual utilice directamente los núcleos de la CPU. Un espacio de TrueNAS, está dedicado para las copias de seguridad de los contenedores del NODO1, este espacio está compartido mediante NFS, y está asignado al propio PROXMOX.
CONSUMOS NODO 2:
![image](https://github.com/user-attachments/assets/6e920980-fa33-4240-be01-4b6471b62c1b)


![image](https://github.com/user-attachments/assets/5818c098-8522-47f3-91f1-1e8a17752d91)

CÓPIAS DE SEGURIDAD:
Mi política de copias de seguridad, es muy simple. Los contenedores que corren en el NODO 1, se hace una copia de seguridad en el espacio NFS, compartido por TrueNAS, luego estas copias se mandan a MEGA. Actualmente, tengo configurado que se realice 1 copiá de cada contenedor a principio de cada mes, ya que estos contenedores a penas sufren cambios. También realizo copias de las carpetas compartidas mas relevantes, que también son enviadas a MEGA. 
![image](https://github.com/user-attachments/assets/5ea02907-65ec-4146-833f-f0530df6ffda)
![image](https://github.com/user-attachments/assets/6091a0c8-2d8a-4caf-bae4-7b1b9aa27a25)
![image](https://github.com/user-attachments/assets/768b7a18-3fc2-4962-a127-c8590f55e9ba)




## UPDATES
OBVIAMENTE TENGO PENSADO HACER UPDATES

