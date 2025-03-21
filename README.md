# -Automated-Static-Site-Hosting-on-AWS-S3-with-Terraform
Ce projet automatise le déploiement d'un site web statique sur AWS S3 en utilisant Terraform. Il permet de configurer un bucket S3 en mode site web, de gérer les permissions et d'uploader les fichiers statiques (index.html, error.html).
📌 Description
Ce projet automatise le déploiement d'un site web statique sur AWS S3 en utilisant Terraform. Il permet de configurer un bucket S3 en mode site web, de gérer les permissions et d'uploader les fichiers statiques (index.html, error.html).

📦 Fonctionnalités
✅ Création automatique d'un bucket S3 et configuration en mode site web
✅ Gestion des permissions pour un accès public sécurisé
✅ Déploiement de fichiers HTML (index.html, error.html) avec public-read
✅ Configuration d'une page d'erreur personnalisée
✅ Infrastructure as Code (IaC) avec Terraform

🔧 Prérequis
Terraform installé
Un compte AWS avec des credentials configurés

🚀 Déploiement
Initialiser Terraform
```bash
terraform init
```
Planifier le déploiement
```bash
terraform plan
```
Appliquer les changements
```bash
terraform apply -auto-approve
```
Une fois le déploiement terminé, tu obtiendras l'URL du site hébergé sur S3. 🎉
