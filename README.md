# Déploiement d’un Réseau Segmenté avec VLANs et Routage Statique

## Description
Ce projet consiste à configurer un **réseau d’entreprise segmenté** avec VLANs et routage statique. L’objectif est de **sécuriser le trafic**, **optimiser la bande passante** et permettre la communication entre départements et sites distants.

## Technologies utilisées
- **VLANs** : segmentation des départements (Administration, Commercial, Technique)  
- **Router-on-a-Stick** : routage inter-VLAN via sous-interfaces sur R1  
- **EtherChannel** : agrégation de liens entre switches pour redondance et bande passante  
- **Routage statique** : interconnexion des sites distants et communication inter-VLAN  

## Topologie et adressage
| VLAN | Réseau IP          | Masque          | Passerelle       |
|------|------------------|----------------|----------------|
| 10   | 172.18.10.0       | 255.255.255.240 | 172.18.10.14   |
| 20   | 172.18.20.0       | 255.255.255.240 | 172.18.20.14   |
| 30   | 172.18.30.0       | 255.255.255.240 | 172.18.30.14   |
| 50   | 172.18.50.0 (natif)| 255.255.255.240 | 172.18.50.14  |
| 60   | 172.18.60.0 (Admin)| 255.255.255.240 | 172.18.60.14  |

Les sites distants utilisent le bloc **10.0.30.128/25** pour les liaisons point à point et les réseaux PC.

## Configuration
- **Switches (S1 & S2)** : création des VLANs, ports d’accès assignés, trunks et EtherChannel pour agrégation.  
- **Routeur R1** : sous-interfaces pour chaque VLAN, encapsulation dot1q, routage inter-VLAN.  
- **Routeurs R2 & R3** : interfaces séries configurées, routes statiques pour l’interconnexion des sites.  

## Tests et validation
- Connectivité **inter-VLAN** via Router-on-a-Stick  
- Ping vers les sites distants pour vérifier les **routes statiques**  
- Accessibilité aux interfaces de gestion (SVI)  

## 🎥 Vidéo du projet

[![Déploiement Réseau VLANs et Routage Statique](https://img.youtube.com/vi/M55ntfwHQVM/0.jpg)](https://youtu.be/M55ntfwHQVM)


## Auteur
**Ilyas Sekhsoukhi**
