# Custom Caddy Image

A containerized build of Caddy with pre-installed plugins.

## Included Plugins

- **nginx-adapter**: Converts Nginx config to Caddy
- **caddy-teapot-module**: Returns HTTP 418 I'm a teapot responses
- **Cloudflare DNS**: Supports Cloudflare DNS provider for ACME challenges

## Supported Architectures

- `linux/amd64` (x86-64)
- `linux/arm64` (ARM v8)

## Usage

Pull from GitHub Container Registry:

```bash
docker pull ghcr.io/rdiazlugo/caddy
```

Or from Docker Hub:

```bash
docker pull reinaldo122/caddy
```

## Build Locally

```bash
docker build -t my-caddy .
```

## How It Works

The Dockerfile uses a multi-stage build:

1. **Builder stage**: Compiles Caddy with plugins using `xcaddy`
2. **Runtime stage**: Uses the official Caddy image with the custom binary

This approach keeps the final image minimal while including all necessary functionality.
