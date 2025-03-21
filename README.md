# 🌍 Déploiement d'un Site Statique sur AWS S3 avec Terraform

![Déploiement](deploiment.png)

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

## 📜 Code Terraform

```hcl
resource "aws_s3_bucket" "mybucket" {
  bucket = var.bucketname
}

resource "aws_s3_bucket_ownership_controls" "example" {
  bucket = aws_s3_bucket.mybucket.id

  rule {
    object_ownership = "BucketOwnerPreferred"
  }
}

resource "aws_s3_bucket_public_access_block" "example" {
  bucket = aws_s3_bucket.mybucket.id

  block_public_acls       = false
  block_public_policy     = false
  ignore_public_acls      = false
  restrict_public_buckets = false
}

resource "aws_s3_bucket_acl" "example" {
  depends_on = [
    aws_s3_bucket_ownership_controls.example,
    aws_s3_bucket_public_access_block.example
  ]

  bucket = aws_s3_bucket.mybucket.id
  acl    = "public-read"
}

resource "aws_s3_object" "index" {
  bucket = aws_s3_bucket.mybucket.id
  key = "index.html"
  source = "index.html"
  acl= "public-read"
  content_type = "text/html"
}

resource "aws_s3_object" "error" {
  bucket = aws_s3_bucket.mybucket.id
  key = "error.html"
  source = "error.html"
  acl= "public-read"
  content_type = "text/html"
}

resource "aws_s3_bucket_website_configuration" "website" {
  bucket = aws_s3_bucket.mybucket.id
  index_document {
    suffix = "index.html"
  }
  error_document {
    key="error.html"
  }

  depends_on = [ aws_s3_bucket_acl.example ]
}

output "mybucket" {
  value = aws_s3_bucket.mybucket.id
}
```

## 📸 Captures d'Écran

### 📌 Configuration ACL
![ACL](acl.png)

### 📌 Autorisations
![Autorisation](autorisation.png)

### 📌 Déploiement en cours
![Déploiement](deploiment.png)

### 📌 Page d'erreur
![Page d'erreur](errorpage.png)

### 📌 Index.html
![Index](index.png)

### 📌 Affichage des pages
![Pages](pages.png)

## 🎯 Résultat final
Une fois le déploiement terminé, votre site statique sera accessible via l'URL générée par AWS S3.

🚀 **Bon déploiement !**
