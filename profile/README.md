# Algonius

<div align="center">
  <img src="assets/logo.jpeg" alt="Algonius Logo" width="200"/>
  <h3>AI Quantitative Trading Platform on Blockchain</h3>
  <p>Blockchain-native AI quantitative trading platform with social sentiment analysis</p>

  [![License](https://img.shields.io/github/license/algonius/algonius)](LICENSE)
  [![Discord](https://img.shields.io/discord/1234567890)](https://discord.gg/algonius)
  [![Twitter Follow](https://img.shields.io/twitter/follow/algonius?style=social)](https://twitter.com/algonius)
</div>

## Introduction

Algonius is a complete MEME token quantitative trading solution that integrates:

- 🤖 AI-driven trading bot
- 📊 Sentiment & technical analysis
- 💼 Multi-chain asset management
- 🎮 User-friendly console
- 🔔 Multi-channel notification system

## Project Features

### Quantitative Trading Framework
- Modular architecture with strategy engine, signal handling, and risk management
- Support for AI-driven trading strategies
- Blockchain-native trading execution
- Real-time market data processing
- Customizable trading strategies via plugins
- Built-in risk management system

### Plugin System
- Extensible architecture through independent plugins
- Support for multiple blockchain protocols (Solana, Sui, etc.)
- Custom notification channels (Telegram, etc.)
- Standardized plugin interface and communication protocol
- Easy to develop and integrate new plugins

## System Architecture

````mermaid
graph TB
    subgraph Frontend["User Access"]
        A1[algonius-web]
        A2[algonius-tg]
        A3[algonius-extension]
    end

    subgraph API["Management Layer"]
        B[algonius-api]
    end

    subgraph Core["Trading Core"]
        C1[algonius-bot-1]
        C2[algonius-bot-2]
        C3[algonius-bot-n]
    end

    subgraph External["External Interface"]
        D1[Blockchain RPC]
        D2[DEX Protocol]
        D3[Social Media]
        D4[Web Data Source]
    end

    A1 --> B
    A2 --> B
    A3 --> B
    A3 --> D4
    B --> C1
    B --> C2 
    B --> C3
    C1 --> External
    C2 --> External
    C3 --> External
````

## Directory Structure

```
.
├── cmd/                 # Main application entrypoints
│   └── algonius-bot/    # Core trading bot CLI
│       ├── command/     # CLI command definitions
│       └── conf/        # Configuration loading

├── internal/            # Private application components
│   └── algonius-bot/
│       ├── api/         # Trading API handlers
│       ├── engine/      # Core trading logic
│       ├── strategy/    # Default trading strategies
│       └── notify/      # Notification system

├── pkg/                 # Shared library code
│   ├── core/            # Framework core interfaces
│   │   ├── configs/     # Configuration management
│   │   └── plugin/      # Plugin system core

├── plugins/             # Plugin implementations
│   ├── plugin-notify-telegram/  # Telegram notification
│   ├── plugin-solana/   # Solana blockchain adapter
│   └── plugin-sui/      # Sui blockchain adapter

├── configs/             # Configuration templates
│   └── strategy/        # Strategy configurations

└── test/                # Test infrastructure
    └── integration/     # E2E test cases
```

## Quick Start

### Prerequisites
- Go 1.23 or higher
- Make

### Installation
1. Clone the repository
```bash
git clone https://github.com/algonius/algonius.git
cd algonius
```

2. Build the project
```bash
make build
```

3. Run with default configuration
```bash
make run
```

### Telegram Bot
1. Open [@algonius_bot](https://t.me/algonius_bot)
2. Send `/start` to begin
3. Follow the setup guide

### Web Client
Visit [http://localhost:3000](http://localhost:3000) to get started

## Build & Run

### Makefile Commands

```bash
# Complete build (main program + plugins)
make build

# Build plugins only
make plugins

# Build main program only
make main

# Run trading bot (auto builds before running)
make run

# Run unit tests
make test-unit

# Run integration tests
make test-integration

# Run all tests
make test

# Clean build artifacts
make clean
```

## Configuration

The configuration files are located in the `configs/` directory:

- `configs/config.yaml`: Main configuration file
- `configs/strategy/*.yaml`: Strategy-specific configurations

Example configuration:
```yaml
strategy:
  name: ai_bot
  params:
    risk_level: medium
    max_position: 1000

plugins:
  - name: solana
    enabled: true
  - name: telegram
    enabled: true
```

## Plugin Development

To create a new plugin:

1. Create a new directory under `plugins/`
2. Implement the plugin interface defined in `pkg/core/plugin`
3. Add plugin configuration to `configs/config.yaml`

See `docs/PluginDev.md` for detailed plugin development guide.

## Testing

```bash
# Run all tests
make test

# Run specific test suites
make test-unit      # Unit tests only
make test-plugins   # Plugin tests
make test-main     # Main program tests
make test-integration  # Integration tests
```

## Roadmap

### 2024 Q4
- [x] MVP Release
- [ ] Web Console Basic Features
- [ ] Multi-user Support
- [ ] Basic Monitoring & Alerts
- [ ] Telegram Bot Initial Release

### 2025 Q1
- [ ] Browser Extension Development
- [ ] Advanced Strategy Orchestration
- [ ] Performance Optimization
- [ ] Security Hardening
- [ ] AI Strategy Improvements
- [ ] Telegram Bot Enhancement

### 2025 Q2
- [ ] SaaS Service
- [ ] Enterprise Version
- [ ] More Chain Support
- [ ] Community Ecosystem
- [ ] Browser Extension Advanced Features
- [ ] Multi-platform Integration

## Community

- [Discord](https://discord.gg/algonius)
- [Twitter](https://twitter.com/algonius)
- [Telegram](https://t.me/algonius_chat)

## Contributing

We welcome all forms of contributions:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

See [Contributing Guide](CONTRIBUTING.md) for details.

## Documentation

- Technical Documentation: `docs/Tech.md`
- API Documentation: `docs/API.md`
- Plugin Development Guide: `docs/PluginDev.md`

## Support

For support and questions:
- GitHub Issues
- Documentation
- Community Discord/Telegram (Coming soon)

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Contact

- Email: hello@algonius.ai
- Twitter: [@algonius](https://twitter.com/algonius)
- Telegram: [@algonius_admin](https://t.me/algonius_admin)
