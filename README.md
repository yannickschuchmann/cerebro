# Cerebro

This project sets up a Docker-based environment to run SLMs on a VPS. It comes with Traefik as a reverse proxy, n8n for workflow automation, STAPI for text embedding, and Open WebUI for Ollama.

## Prerequisites

- Docker and Docker Compose
- A domain name

## Setup

1. Clone this repository.

2. Copy the `.env.dist` file to `.env` and fill in the required values:

   ```
   DOMAIN_NAME=your-domain.com
   N8N_SUBDOMAIN=n8n
   GENERIC_TIMEZONE=Your/Timezone
   SSL_EMAIL=your-email@example.com
   HF_TOKEN=your-huggingface-token
   ```

3. Run the following command to start the services:

   ```
   docker compose up -d
   ```

## Services

- **Traefik**: Reverse proxy and SSL termination
  - Dashboard: https://your-domain.com:8080
- **n8n**: Workflow automation
  - URL: https://n8n.your-domain.com
- **STAPI**: Text embedding service
  - URL: https://stapi.your-domain.com
- **Open WebUI**: Interface for Ollama
  - URL: https://openwebui.your-domain.com

## SSL Certificates

SSL certificates are automatically generated and renewed using Let's Encrypt.

## Data Persistence

Data for each service is persisted using Docker volumes:

- traefik_data
- n8n_data
- ollama_data
- open-webui_data

## Security

Ensure to keep your `.env` file secure and never commit it to version control.

## Support

For issues or questions, please open an issue in the project repository.
