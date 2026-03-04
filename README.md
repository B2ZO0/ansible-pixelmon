🛡️ Infrastructure Pixelmon sur Proxmox - SIO 24-26 Ce projet présente l'automatisation du déploiement d'un écosystème Minecraft moddé (Pixelmon) via Ansible sur des conteneurs LXC Debian 12.

📝 Présentation du projetL'objectif est de maintenir une infrastructure de serveurs de jeu hautement disponibles. Le projet gère l'installation de Java 11 la configuration de Forge 1.16.5 et la synchronisation des mods entre le serveur et le client macOS.

🌐 Détails du Réseau & InfrastructureHôte de Virtualisation (Proxmox) : 10.2.0.253 Serveur Pixelmon Principal (CT 502) : 10.2.0.50 Serveur Pixelmon Secondaire (CT 503) : 10.2.0.51 [cite: 2026-01-04]Client de Management (MacBook Pro) : 10.2.0.131🛠️ Guide des Commandes EssentiellesDéploiement Ansible (Automatisation) Bash# Lancer le déploiement complet des deux serveurs
ansible-playbook -i inventory.ini deploy_pixelmon.yml

Administration Système & MinecraftBash# Accéder à la console du serveur en direct
screen -r pixelmon

# Quitter la console sans éteindre le serveur
Ctrl + A puis D

# Vérifier la version Java installée
java -version
Gestion du Code (Git)Bash# Sauvegarder les changements sur GitHub
git add .
git commit -m "Mise à jour de l'infrastructure"
git push
