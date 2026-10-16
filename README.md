# Weather MCP Server

An [Model Context Protocol (MCP)](https://modelcontextprotocol.io/) server that
provides weather information from the United States National Weather Service
(NWS) API.

## Features

- Retrieve active weather alerts for a US state.
- Retrieve the next five forecast periods for a latitude and longitude.
- Run over the MCP standard input/output transport for use with MCP clients.

## Requirements

- Python 3.14 or newer
- [uv](https://docs.astral.sh/uv/)

The NWS API is free and does not require an API key. Requests identify
themselves with the `weather-app/1.0` user agent.

## Installation

Clone the repository and install its dependencies with uv:

```bash
uv sync
```

## Usage

Start the MCP server:

```bash
uv run weather.py
```

The server exposes these tools:

### `get_alerts`

Returns active alerts for a two-letter US state code:

```text
state: CA
```

### `get_forecast`

Returns the next five forecast periods for a location:

```text
latitude: 38.9072
longitude: -77.0369
```

## Development

Run the project using the locked dependency set:

```bash
uv run weather.py
```

The server communicates over stdio, so it should generally be launched by an
MCP-compatible client rather than opened directly in a terminal.

## License

No license has been selected for this project yet.