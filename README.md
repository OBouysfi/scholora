# Scholora - Guide d'installation et d'exécution

Bienvenue dans le projet **Scholora**. Ce guide explique comment cloner, configurer, démarrer et accéder aux différentes parties du projet, incluant le backend Laravel et le frontend React.

---

## **#1. Cloner le projet**

Clonez le dépôt sur votre machine locale et accédez au répertoire cloné :
```bash
git clone https://github.com/OBouysfi/scholora.git
cd scholora

#2. Configurer et démarrer avec Docker

cd docker
docker-compose down
docker-compose up -d

#3. Accéder aux services

Une fois les conteneurs démarrés, vous pouvez accéder aux services suivants :

Laravel Backend : http://localhost:9100
React Frontend : http://localhost:3100
PhpMyAdmin : http://localhost:8081
SonarQube : http://localhost:9001
Scholora App : http://scholora.com

#4. Vérification DNS

Pour accéder à scholora.com, assurez-vous que votre machine locale pointe correctement. Modifiez le fichier hosts :

 1. Ouvrez le fichier hosts :

-  Windows : C:\Windows\System32\drivers\etc\hosts
-  Linux/Mac : /etc/hosts
 2. Ajoutez cette ligne :
  127.0.0.1 scholora.com

 3. Vérifiez que le domaine fonctionne :
  ping scholora.com

#5. Configurer Laravel

docker exec -it scholora-app bash
cd /var/www/html
composer install
php artisan config:cache
php artisan route:cache
exit

#6. Configurer React
http://localhost:3100



