# 🌍 Déploiement d'un Site Statique sur AWS S3 avec Terraform


## 📌 Description
Ce projet montre comment utiliser **Terraform** pour déployer un site statique sur **AWS S3** en activant l'hébergement statique et en définissant les permissions nécessaires.

## 🛠 Technologies utilisées
- 🌿 **Terraform**
- ☁️ **AWS S3**
- 🔐 **ACL & IAM Policies**
- 🌍 **Hébergement statique**

## 📂 Structure du Projet
```
📁 s3-static-site
│── 📄 main.tf       # Code Terraform
│── 📄 variables.tf  # Variables Terraform
│── 📄 provider.tf   # Définir les fournisseurs
│── 📄 index.html    # Page principale
│── 📄 error.html    # Page d'erreur
│── 📄 README.md     # Documentation
│── 📁 images        # Captures d'écran
```

## 🚀 Déploiement avec Terraform
### 📌 Étape 1: Initialisation de Terraform
```sh
terraform init
```

### 📌 Étape 2: Planification
```sh
terraform plan
```

### 📌 Étape 3: Application des configurations
```sh
terraform apply -auto-approve
```

## 📸 Captures d'Écran

### 📌 Configuration ACL
![ACL](/images/acl.png)

### 📌 Autorisations
![Autorisation](/images/autorisation.png)

### 📌 Déploiement en cours
![Déploiement](/images/deploiment.png)

### 📌 Page d'erreur
![Page d'erreur](/images/errorpage.png)

### 📌 Index.html
![Index](/images/index.png)

### 📌 Affichage des pages
![Pages](/images/pages.png)

## 🎯 Résultat final
Une fois le déploiement terminé, votre site statique sera accessible via l'URL générée par AWS S3.

🚀 **Bon déploiement !**
