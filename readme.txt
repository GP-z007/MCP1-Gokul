# PentestSidecar MCP Server

A Model Context Protocol (MCP) server that provides container hosting with sidecar architecture for pentesting environments.

## Purpose

This MCP server simplifies deployment and management of containerized pentesting setups using sidecar containers for logging, monitoring, and security. It enables easy environment configuration, graceful shutdowns, crash validation, and security by segregating auxiliary tasks into sidecars.

## Features

### Current Implementation

- **list_containers** - Lists running containers including sidecars.
- **start_container** - Starts a container with optional sidecar container.
- **stop_container** - Stops a container and its sidecar gracefully.
- **get_logs** - Fetches logs from a given container.
- **run_pentest_tool** - Runs common pentesting tools inside containers on specified targets.
- **validate_container** - Checks container status and restart count for crashes.

## Prerequisites

- Docker Desktop with MCP Toolkit enabled
- Docker MCP CLI plugin (`docker mcp` command)
- Local Docker daemon with Docker CLI accessible

## Installation

Follow the installation instructions provided separately.

## Usage Examples

In Claude Desktop, you can ask:

- "List all running containers"
- "Start a container named webapp with nginx image and sidecar for monitoring"
- "Stop the container webapp and its sidecar"
- "Get the last 50 logs from container webapp"
- "Run nmap against 192.168.1.10 inside container pentest-tool"
- "Validate if container webapp is running and healthy"

## Architecture

Claude Desktop → MCP Gateway → PentestSidecar MCP Server → Docker daemon (local)

↓

Docker Desktop Secrets

## Development

### Local Testing

