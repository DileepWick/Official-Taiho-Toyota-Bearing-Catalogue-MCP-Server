# Official Taiho Toyota Bearing Catalogue MCP Server

[![Protocol](https://img.shields.io/badge/MCP-1.0.0-blue)](https://modelcontextprotocol.io)
[![Monetization](https://img.shields.io/badge/Monetization-X402--v2-gold)](https://x402.org)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

An authoritative Model Context Protocol (MCP) server providing technical specifications for Toyota engine bearings. Data is sourced directly from the **Official Taiho Catalogue**, ensuring high-fidelity engineering parameters for automotive AI agents, procurement systems, and technical researchers.

## Overview

This server exposes a suite of tools to query precise bearing data, including shaft/housing diameters, wall thickness, and length. It is optimized for programmatic discovery and integration into LLM-based workflows.

## Integration Specification

### Client Configuration

To integrate this server with a compatible MCP client (e.g., Claude Desktop, Cursor, or a custom agentic framework), use the following transport configuration:

```json
{
  "mcpServers": {
    "taiho-catalogue-official": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/sdk",
        "mcp-remote",
        "https://my-mcp-server.wickramasinghemgdd.workers.dev/mcp"
      ]
    }
  }
}
```

## Tool Definitions

### Public Access (Free)

- `search_by_engine`: Query technical specifications by Toyota engine code (e.g., `4A-GE`, `2AD-FTV`). Supports partial matching.
- `list_engines`: Returns an exhaustive list of all 200+ supported Toyota engine codes currently indexed.

### Premium Access (Monetized via X402)

_Usage of these tools requires an X402-compatible client and payment facilitation._

- `search_by_car`: Query bearings by vehicle model name (e.g., `COROLLA`, `RAV4`, `LEXUS IS`). **Cost: 0.01 USD / call**.
- `search_by_part_no`: Reverse lookup by Taiho Set Number, Part Number, or OEM Reference. **Cost: 0.01 USD / call**.

## Protocol & Monetization

| Attribute       | Specification                                |
| :-------------- | :------------------------------------------- |
| **MCP Version** | 1.0.0                                        |
| **Network**     | Base Mainnet (eip155:8453)                   |
| **Protocol**    | X402 v2                                      |
| **Facilitator** | `https://x402.org/facilitator`               |
| **Recipient**   | `0x48fB3bF606C012127d72A5B1FaB372B3676b14EF` |

## Technical Capabilities

- **Dimensional Accuracy**: Provides shaft diameter, housing diameter, wall thickness, and length.
- **Comprehensive Coverage**: Includes Main, Rod, and Thrust bearing specifications.
- **OEM Mapping**: Direct cross-referencing between Taiho and Toyota OEM part numbers.

## License

This repository contains the documentation and connection manifest for the Taiho Toyota Bearing MCP service. These assets are licensed under the **MIT License**. Use of the hosted MCP endpoint is subject to protocol-level monetization and terms of service.
