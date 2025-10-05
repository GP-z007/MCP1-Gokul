# PentestSidecar MCP Server Implementation Details

- **Purpose:** Container hosting with sidecar-first architecture designed to simplify deployment, monitoring, logging, security, and pentesting workloads.
- **Language Agnostic:** Does not depend on application language; manages containers at Docker level.
- **Sidecars:** Optional sidecar containers for logging/monitoring/security, linked to main containers.
- **Tools Provided:**
  - Container lifecycle management (start, stop, list)
  - Log retrieval
  - Web pentesting tool execution inside containers (e.g., nmap, nikto)
  - Container health validation
- **Logging:** All major actions logged to stderr; user-friendly error messages.
- **Graceful Shutdown:** Stop containers and sidecars cleanly via Docker commands.
- **Security:** 
  - Runs under a non-root user within Docker container.
  - Docker container isolation leveraged.
- **Dependencies:** Python MCP server, Docker CLI, httpx.
- **Environment:** Runs in Docker container with Python 3.11 slim base image.
- **Error Handling:** Robust error checks and meaningful user-facing messages.
- **Extensibility:** New MCP tools can be added easily following MCP conventions.

## Development Instructions

- Follow MCP tool guidelines.
- Ensure no multi-line docstrings; use single-line only.
- Validate input parameters for safety.
- Use Docker for both development and deployment to mirror production.

## User Instructions

- Build Docker image using provided Dockerfile.
- Add custom MCP catalog and registry entries for Claude Desktop integration.
- Use provided commands over MCP interface in Claude Desktop for container management and pentesting.

## Notes

- Designed for educational pentesting within controlled environments.
- Does not expose external APIs or require external tokens currently.
- Extendable for advanced pentesting scenarios and monitoring integrations.
