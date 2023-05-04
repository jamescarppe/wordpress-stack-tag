# wordpress-stack-tag

A basic WordPress stack (WordPress container and MySQL database) which uses environment-variable defined image tags, for use with Portainer and Portainer's webhook functionality.

## Usage

1. Deploy the stack from the Git repository with Portainer, enabling webhooks
1. Use the webhook with the environment variable as an option (per the [documentation](https://docs.portainer.io/user/docker/stacks/webhooks#using-environment-variables-with-webhooks)) to update the image tag.  
    
   For example, to update the `wordpress` container to the `php8.1` image tag:  
     
   ```
   http POST https://portainer:9443/api/stacks/webhooks/4adace48-e065-44f2-abdd-93c797760eef?WORDPRESS_TAG=php8.1
   ```
   
   The `wordpress` container will be redeployed with the `php8.1` image tag. The `db` container will remain untouched, as no changes were requested for it.
