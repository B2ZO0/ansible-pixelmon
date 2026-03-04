🛡️ Infrastructure Pixelmon sur ProxmoxCe projet présente l'automatisation et le déploiement d'un écosystème Minecraft moddé (Pixelmon) utilisant des conteneurs LXC et Ansible.📝 Présentation du projetL'objectif est de déployer deux serveurs de jeu synchronisés sur un cluster Proxmox. Le projet inclut la gestion des versions Java spécifiques la configuration des ports réseau et la mise en place d'un environnement client compatible sur macOS.🌐 Détails du RéseauHôte Proxmox (pve-02) : 10.2.0.253Serveur Pixelmon Principal (502) : 10.2.0.50Serveur Pixelmon Secondaire (503) : 10.2.0.51 [cite: 2026-01-04]Client de Gestion (Mac) : 10.2.0.131🛠️ Guide des Commandes EssentiellesDéploiement AnsibleBash# Lancer l'installation complète sur les serveurs 502 et 503
ansible-playbook -i inventory.ini deploy_pixelmon.yml
Administration du ServeurBash# Entrer dans la console du serveur (Screen)
screen -r pixelmon

# Sortir de la console sans couper le serveur
Ctrl + A puis D

# Forcer le redémarrage (via le script personnalisé)
./start.sh
Gestion Git & SécuritéBash# Sauvegarder les modifications sur GitHub
git add .
git commit -m "Mise à jour de la configuration"
git push

# Mémoriser les identifiants (Token) pour éviter les saisies répétées
git config --global credential.helper store [cite: 2026-01-04]
⚠️ Journal des Erreurs & Résolutions (Post-Mortem)Erreur rencontréeCause identifiéeSolution appliquéeJava Runtime LocationLe système ne trouvait pas Java lors du lancement de ForgeInstallation de temurin@11 via Homebrew sur Mac [cite: 2026-01-04]Authentication FailedTentative de connexion Git avec mot de passe (obsolète)Création et utilisation d'un Personal Access Token (PAT) [cite: 2026-01-04]Version MismatchConfusion entre l'installeur 1.20 et le serveur 1.16.5Suppression du mauvais .jar et téléchargement de la version 36.2.34Repository not foundLe dépôt distant n'existait pas encore sur l'interface WebCréation manuelle du repo ansible-pixelmon sur GitHubUnable to access jarfileMauvais chemin spécifié dans le terminalUtilisation du glisser-déposer pour obtenir le chemin absolu du fichier
