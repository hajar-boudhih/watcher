
# watcher

# 🔗 CHAINSOC - The Watcher (Machine 1)

##  Mon rôle dans le projet

Je suis **Personne 1 - The Watcher**. Mon rôle est de construire le système de surveillance et de vérification d'intégrité des logs. Je suis le cerveau du système ChainSOC.

---

## 📋 Ce que j'ai fait exactement

### 1. Configuration de la machine virtuelle

- Création d'une VM avec **Ubuntu Desktop 22.04**
- Configuration réseau en  pour communiquer avec les autres machines
- Allocation : 4GB RAM, 25GB disque

### 2. Installation des outils essentiels

| Outil | Version | Utilité |
|-------|---------|---------|
| Python 3 | 3.10+ | Scripts de hash et détection |
| Node.js | 18.x | Dashboard React |
| React | latest | Interface utilisateur |
| Nerdlog | 1.10.0 | Requêtage de logs distant |
| Web3.py | - | Interaction avec blockchain |
| Cryptography | - | Chiffrement AES-256 |

### 3. Scripts Python développés

| Script | Fonction | Performance |
|--------|----------|-------------|
| `hash_log.py` | Calcule le hash SHA-256 d'un fichier | 0.0006s pour 100K lignes |
| `encrypt_logs.py` | Chiffrement AES-256 des logs | Clé générée automatiquement |
| `incident_detector.py` | Détection d'incidents en temps réel | 4 règles actives |
| `alert_manager.py` | Gestion et stockage des alertes | Stockage JSON |
| `final_verification.py` | Vérification complète du système | Teste SSH + blockchain |

### 4. Règles de détection YAML

Fichier : `rules/security_rules.yaml`

| Règle | Pattern | Seuil | Sévérité |
|-------|---------|-------|----------|
| brute_force_attack | "Failed password" | 5 en 60s | Critique |
| suspicious_sudo | "sudo.*FAILED" | 3 en 300s | Élevée |
| invalid_user | "Invalid user" | 3 en 60s | Élevée |
| root_access | "Accepted.*root" | 1 | Critique |

### 5. Dashboard React

- Interface utilisateur complète
- Affichage des logs en temps réel
- Panneau d'alertes intégré
- Connexion SSH simulée (prête pour intégration)
- Connexion blockchain simulée (prête pour intégration)

### 6. Configuration SSH

- Génération d'une clé SSH pour connexion sécurisée
- Configuration de Nerdlog pour interroger Machine 3

---

## Ce qu'on peut faire sur le dashboard

### Écran principal

Le dashboard est accessible à l'adresse : `http://localhost:3000`

### 1. Voir l'état du système

| Carte | Information affichée |
|-------|---------------------|
| **VAULT NETWORK** | Statut de la blockchain (ONLINE/OFFLINE) |
| **TARGET SYSTEM** | Statut de la connexion SSH (ACCESSIBLE/LOCKED) |
| **SYSTEM HEALTH** | Barres de progression pour Blockchain, SSH, Logs |

### 2. Contrôler le système

| Bouton | Action |
|--------|--------|
| **CONNECT TO VAULT** | Établit la connexion avec la blockchain (Machine 2) |
| **ESTABLISH SSH** | Établit la connexion SSH avec la Machine 3 |
| **FETCH LOGS** | Récupère les logs depuis Machine 3 |
| **REFRESH** | Rafraîchit le dashboard |

### 3. Visualiser les alertes

Le panneau **ALERTES DE SÉCURITÉ** affiche :

- Les alertes critiques (rouge)
- Les alertes élevées (orange)
- Les alertes moyennes (jaune)
- La date et l'heure de chaque alerte
- La source de l'alerte

### 4. Analyser les logs

Dans la section **LOG HISTORY** :

- Cliquer sur un log pour voir ses détails
- Afficher le contenu brut du log
- Afficher le hash SHA-256

### 5. Vérifier l'intégrité

Dans le panneau **LOG ANALYSIS** :

| Bouton | Action |
|--------|--------|
| **STORE ON BLOCKCHAIN** | Stocke le hash du log sur la blockchain |
| **VERIFY INTEGRITY** | Vérifie si le log a été modifié |
| **SIMULATE ATTACK** | Simule une falsification du log |

### 6. Résultats de vérification

| Résultat | Affichage |
|----------|-----------|
| Log intact |  INTEGRITY VERIFIED (vert) |
| Log falsifié | ⚠ SECURITY ALERT (rouge) |

---

## Résumé des fonctionnalités du dashboard


<img width="1529" height="765" alt="image" src="https://github.com/user-attachments/assets/e4d9b0bf-f905-44fc-ae7f-c6dd6108b926" />

<img width="1498" height="706" alt="image" src="https://github.com/user-attachments/assets/57453484-387f-4964-8f55-68534db5cf2e" />

