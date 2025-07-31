# tofu-docker-nginx

A simple tofu module that starts an NGINX container using the kreuzwerker/docker provider. This module is created simply for educational purposes. It teaches the handling with modules and the OpenTofu registry

## Usage
1. Include the following module definition in your Tofu scripts
```hcl
module "nginx" {
  source         = "github.com/jamaicabot/terraform-docker-nginx"
  image_name     = "nginx:alpine"
  container_name = "meine-nginx"
  port           = 8080
  
  # Database configuration parameters
  db_container_id = "<your_db_container_id>"
  db_host         = "<your_db_host>"
  db_port         = "<your_db_port>"
  db_password     = "<your-db-password>"
}
```
2. Run `tofu init` and the module will automatically will be downloaded to your local environment.