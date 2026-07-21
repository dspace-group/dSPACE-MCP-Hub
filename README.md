# dSPACE MCP Hub

**The MCP Hub for Agentic, Specification-Driven Engineering Workflows**

The **dSPACE MCP Hub** provides a unified collection of MCP servers that connect AI assistants directly to the dSPACE toolchain.

Built on the **Model Context Protocol (MCP)**, an open standard that enables AI assistants to interact with tools, data sources, and engineering applications in a contextual and controlled manner.

---

## Why MCP Hub?

Modern engineering workflows span multiple tools and engineering artifacts:

- Requirements and work items
- System architectures and specifications
- Software and model development
- Simulation and virtual validation
- Hardware integration
- Calibration and measurement
- Automated testing and validation

Although these activities are connected logically, they are often disconnected operationally, requiring engineers to manually switch between tools, transfer context, and coordinate engineering artifacts.

The dSPACE MCP Hub enables AI agents to initiate workflows. These are supported from any MCP-compatible AI host. Workflows across various system architectures enabling virtual validation through configuration, measurement and calibration. Engineers-in-loop ensures responsible executing of every action with active review and approval.

## MCP Servers

The Agentic Hub includes MCP servers for core dSPACE products. 

| MCP Server | Git Repository Path |
|------------|-------------|
| **ControlDesk MCP** | [https://github.com/dspace-group/ControlDeskMCP](https://github.com/dspace-group/ControlDeskMCP) |
| **VEOS MCP** | [https://github.com/dspace-group/VeosMCP](https://github.com/dspace-group/VeosMCP) |
| **ConfigurationDesk & Bus Manager MCP** | [https://github.com/dspace-group/ConfigurationDeskBusManagerMCP](https://github.com/dspace-group/ConfigurationDeskBusManagerMCP)  |
| **SystemDesk MCP** | [https://github.com/dspace-group/SystemDeskMCP](https://github.com/dspace-group/SystemDeskMCP) |


### Model Agnostic

The MCP servers work with any coding agent or AI host that supports local MCP over `stdio`. Use your preferred AI assistant and LLM provider with the same server configuration.

Supported examples include:

- GitHub Copilot
- ChatGPT
- Claude
- MCP-compatible AI hosts

### Human-in-the-Loop

AI agents propose actions.

Engineers review, modify, approve, and execute them. Nothing happens without engineering oversight.

---

## Getting Started

Install the server on the Windows machine that has the relevant dSPACE product installed and licensed. Each server runs locally, communicates with its MCP host through standard input and output, and uses `uv` to create its Python environment and install dependencies.

1. Install [uv](https://docs.astral.sh/uv/getting-started/installation/).
2. Clone the required server repository and open its folder.
3. Install its dependencies by running `uv sync`.
4. Register the included `.cmd` launcher with your MCP-compatible coding agent.
5. Reload the MCP servers in the host, then use a status or startup prompt to verify the connection

### GitHub Copilot Example

In the workspace where you use GitHub Copilot, create or update `.vscode/mcp.json`. Replace `<PATH_TO_CLONED_REPOSITORIES>` with the local folder that contains your cloned MCP server repositories.

```json
{
  "SystemDeskMCP": {
   "type": "stdio",
   "command": "<PATH_TO_CLONED_REPOSITORIES>\\SystemDeskMCP\\SystemDeskMCP.cmd"
  },
  "VeosMCP": {
   "type": "stdio",
   "command": "<PATH_TO_CLONED_REPOSITORIES>\\VeosMCP\\VeosMCP.cmd"
  },
  "ConfigurationDeskMCP": {
   "type": "stdio",
   "command": "<PATH_TO_CLONED_REPOSITORIES>\\ConfigurationDeskBusManagerMCP\\ConfigurationDeskMCP.cmd"
  },
  "ControlDeskMCP": {
   "type": "stdio",
   "command": "<PATH_TO_CLONED_REPOSITORIES>\\ControlDeskMCP\\ControlDeskMCP.cmd"
  }
}
```

## Contributing

We welcome contributions from engineers, developers, and AI enthusiasts.

You can contribute by:

- Reporting issues
- Suggesting new MCP capabilities
- Improving documentation
- Sharing examples and best practices

---

## Community

Join us in shaping the future of specification-driven engineering workflows.

Together, we are building the foundation for the next generation of AI-assisted automotive development.

---

**dSPACE MCP Hub**

*Connect engineers, tools, knowledge, and AI agents into a single engineering workflow.*

