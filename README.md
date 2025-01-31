# Cloudflare Tunnel Docker Compose Example

- This setup demonstrates how to securely expose a local Next.js application running in a Docker contianer to the internet using Cloudflare Tunnels. Instead of opening ports or configuring complex networking, Cloudflare Tunnels provides a secure way to route traffic to your local Next.js app.

## Prerequisites
- Cloudflare account with a managed domain
- Docker and Docker Compose installed
- Next.js application running in a Docker container (E.g. [bmorri13/alex_printer_build_counter](https://github.com/bmorri13/alex_printer_build_counter))

## Setup Steps
1. Clone this repository
2. Copy `.env.example` to `.env`
3. Follow the [Cloudflare Tunnels Example](https://tech.aufomm.com/how-to-use-cloudflare-tunnel-to-expose-multiple-local-services/) blog point your domain to Cloudflare (or simply buy a domain from cloudflare), Enable Universl SSL, and Enable Zero Trust
4. Add your Cloudflare Tunnel token to `.env`:
```bash
TUNNEL_TOKEN=your-tunnel-token-here
```

## Usage

### Start up Docker Compose Environment
```bash
docker compose up -d
```

### Check Tunnel Status
```bash
docker logs cloudflared-tunnel
```

### Access Your Application:
- Once running, your Next.js app will be available at: `https://your-configured-domain.com`

### Spin down Docker Compose Environment
```bash
docker compose down
```

## Troubleshooting
- Verify your tunnel token is correct in .env
- Ensure your domain DNS is properly configured in Cloudflare

## Links
- [Cloudflare Tunnels Example](https://tech.aufomm.com/how-to-use-cloudflare-tunnel-to-expose-multiple-local-services/)
- [Cloudflare Tunnels Documentation](https://developers.cloudflare.com/cloudflare-one/connections/connect-apps/)
- [Docker Compose Documentation](https://docs.docker.com/compose/)
- [Next.js Documentation](https://nextjs.org/docs)

## Next Steps
- [Implement CF ZT Authentication](https://www.youtube.com/watch?v=Ynr8VubJqvY)