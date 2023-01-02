# shadowsocks-v2ray-plugin

### Darak

`**WIP**`

### Arvan 

- Enter your domain name from DNS section
- Change nameservers to the one you got in Arvancloud.

- After your domain nameservers changed successfully.

- Connect your domain to your server's IP address using `A` records. Make sure the `Cloud Service` option is enabled for each record.

- Go to `HTTPS settings` on the navbar, select `Issue certificate`. It will take around 30 minutes for the certificate to be ready.

- After the certificate is issued, enable the `Activate HTTPS` option.

### VPS (`UBUNTU`)

1. SSH into the server.
2. Install docker and docker-compose.
3. go to the vps security group firewall and open 80/TCP - 443/TCP.
4. Clone this repo 
5. Edit the `.env` file.

```bash
# Replace your_domain with the domain you bought, without http, or www in front of it, e.g.: google.com
DOMAIN=your-domain.com

# change to a secure password
PASSWORD=my-new-pass
```

6. Build the docker image and run the containers with below commands:

```bash
docker-compose build

docker-compose up -d
```

7. Since the container is running in detached mode, you need to check the logs to see the config for your VPN server. (Android and iOS urls)

```bash
docker-compose logs -f --tail 500
```
