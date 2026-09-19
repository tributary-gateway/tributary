# Tributary

> **Work in Progress** — This project is under active development and not yet ready for production use. APIs, configuration, and documentation may change without notice.

High-throughput, low-latency AI gateway. Route requests across OpenAI, Anthropic, and other providers with built-in rate limiting, cost metering, and streaming support.

## Quick Start

```bash
# Docker
docker run -p 8080:8080 tributary-gateway/tributary:latest

# Binary
curl -fsSL https://github.com/tributary-gateway/tributary/releases/latest/download/tributary-linux-amd64 -o tributary
chmod +x tributary
./tributary serve
```

## Documentation

Full docs: [tributary-gateway.github.io/docs](https://tributary-gateway.github.io/docs)

## Configuration

```yaml
server:
  port: 8080

providers:
  openai:
    api_key: ${OPENAI_API_KEY}
  anthropic:
    api_key: ${ANTHROPIC_API_KEY}

routes:
  - path: /v1/chat/completions
    methods: [POST]
    provider: openai
```

See the [configuration reference](https://tributary-gateway.github.io/docs/configuration) for all options.

## Releases

Pre-built binaries are available for:
- Linux (amd64, arm64)
- macOS (amd64, arm64)

Docker images are published to GHCR:

```bash
docker pull ghcr.io/tributary-gateway/tributary:latest
```

## License

Business Source License 1.1 (BSL 1.1). Free for non-production use. Production use and SaaS require a commercial license. See [LICENSE](LICENSE).

For commercial licensing inquiries, contact [tributary-gateway@protonmail.com](mailto:tributary-gateway@protonmail.com).
