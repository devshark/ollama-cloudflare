## Docker Compose File for Ollama and Cloudflared

This [docker-compose.yml](docker-compose.yml) file sets up a Docker environment for running Ollama, Open-WebUI, and Cloudflare. Here's an overview of what each service does:

**ollama**: Runs the latest version of Ollama, mapping port 11434 to the container.
**webui**: Deploys Open-WebUI, mapping port 9110 to the host machine. It depends on the `ollama` service and uses the API URL from `ollama` to make requests.
**cloudflared**: Runs Cloudflare's cloudflared tool, which sets up a tunnel to the internet. This service depends on the `webui` service.

### Environment Variables

The following environment variables are set for each service:

For `ollama`, you can enable the Ollama API, CLI, or Web UI by setting the corresponding environment variable.
For `webui`, you can configure the API URL, port, and base URL using environment variables.
For `cloudflared`, you need to replace the token with your actual Cloudflare token.
Volumes

The following volumes are mounted:

**ollama**: Maps a volume for storing Ollama data.
**models**: Maps a volume for storing Ollama models.
**open-webui**: Maps a volume for storing Open-WebUI data.
**cloudflared**: Maps a volume for storing Cloudflare configuration files.


### Tunnel Network

The tunnel network is used to connect the services and allow them to communicate with each other.

By running this Docker compose file, you'll have a fully functional Ollama environment with Open-WebUI and Cloudflare tunneling.

### License

[Apache 2.0 License](LICENSE)

### Author

&copy; Anthony Lim
