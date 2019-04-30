Create copy traefik.toml.dist to traefik.toml and edit:

Traefik dashboard username and password (default - **admin:password**)
```toml
[web.auth.basic]
    users = ["admin:$apr1$7kthfemn$D0M22iuDTPx4CbF0QyWAN/"]
```


Domain
```toml
[docker]
    domain = "traefik.domain.com"
```

Email
```toml
[acme]
	email = "mail@mail.com"
```

Create file **acme.json**
```bash
sudo touch acme.json
sudo chmod 600 acme.json
```

Create network:
```bash
sudo docker network create traefik
```

Run:
```bash
sudo docker compose up -d
```


Traefik dashboard will be available at [your_ip]:8080 and your.domain.com. For example:
- http://127.0.0.1:8080
- http://traefik.domain.com

