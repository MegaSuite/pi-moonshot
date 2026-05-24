# @megasuite/pi-moonshot

Pi extension adding [Moonshot AI](https://www.moonshot.ai/) provider support, including the Kimi K2.6 and K2.5 model families.

## Installation

```bash
pi install npm:@megasuite/pi-moonshot
```

Or try without installing:

```bash
pi -e npm:@megasuite/pi-moonshot
```

## Setup

Set your Moonshot API key:

```bash
export MOONSHOT_API_KEY="your-api-key"
```

Or add to your `~/.pi/agent/settings.json`:

```json
{
  "apiKeys": {
    "MOONSHOT_API_KEY": "your-api-key"
  }
}
```

Or add to your `~/.pi/agent/auth.json`:

```json
{
  "moonshot": {
    "type": "api_key",
    "key": "your-api-key"
  }
}
```

## Models

| Model | Description | Context | Reasoning |
|-------|-------------|---------|-----------|
| `kimi-k2.6` | Latest flagship model with vision | 256K | Yes |
| `kimi-k2.5` | Flagship model with vision | 262K | Yes |
| `kimi-latest` | Latest stable version | 131K | No |
| `kimi-k2-turbo-preview` | Fast inference model | 262K | No |
| `kimi-k2-thinking` | Reasoning model | 262K | Yes |
| `moonshot-v1-8k` | Legacy 8K context | 8K | No |
| `moonshot-v1-32k` | Legacy 32K context | 32K | No |
| `moonshot-v1-128k` | Legacy 128K context | 128K | No |

## Switching API Endpoint

Moonshot provides different API endpoints for international and China users. Use the built-in command to switch:

```bash
pi /moonshot-base
```

This will prompt you to choose between:

- `https://api.moonshot.ai/v1` (International)
- `https://api.moonshot.cn/v1` (China)

The selected endpoint will be used for all subsequent Moonshot API requests in the current session.

## Usage

After installation, select a Moonshot model:

```bash
pi /model moonshot/kimi-k2.5
```

Or start pi directly with a Moonshot model:

```bash
pi --provider moonshot --model kimi-k2.5
```

## License

MIT