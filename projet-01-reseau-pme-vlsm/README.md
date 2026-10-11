# Projet 01 : Réseau PME avec adressage VLSM

## Objectif
Concevoir le plan d'adressage IPv4 du siège de Myhappy, une PME fictive de 4 services, en utilisant le VLSM afin de ne pas gaspiller d'adresses.

## Contexte
- Bloc d'adresses disponible : 192.168.10.0/24
- 4 services à connecter, plus une liaison point à point entre deux routeurs

| Service | Machines |
|---------|----------|
| Commercial | 100 |
| Technique (IT) | 50 |
| Comptabilité | 25 |
| Direction | 10 |
| Liaison routeur à routeur | 2 adresses |

## Méthode
1. Pour chaque service, compter les machines + 1 passerelle.
2. Choisir la plus petite puissance de 2 qui convient (formule : 2^n - 2 adresses utilisables).
3. Attribuer les sous-réseaux du plus grand au plus petit pour éviter les chevauchements.
4. Calculer pour chaque bloc : adresse réseau, plage utilisable, broadcast (dernière adresse du bloc).

## Plan d'adressage

| Service | Réseau | Masque | Passerelle | Plage utilisable | Broadcast |
|---------|--------|--------|------------|------------------|-----------|
| Commercial | 192.168.10.0 | /25 (255.255.255.128) | 192.168.10.1 | .1 à .126 | 192.168.10.127 |
| Technique | 192.168.10.128 | /26 (255.255.255.192) | 192.168.10.129 | .129 à .190 | 192.168.10.191 |
| Comptabilité | 192.168.10.192 | /27 (255.255.255.224) | 192.168.10.193 | .193 à .222 | 192.168.10.223 |
| Direction | 192.168.10.224 | /28 (255.255.255.240) | 192.168.10.225 | .225 à .238 | 192.168.10.239 |
| Point à point | 192.168.10.240 | /30 (255.255.255.252) | aucune | .241 et .242 | 192.168.10.243 |

## Topologie
À venir (schéma Packet Tracer).

## Configurations
À venir (dossier `configs/`).

## Vérifications
À venir (dossier `verification/`).

## Ce que j'ai appris
À compléter à la fin du projet.