# Custom Claude Code Configuration

A sophisticated research automation system built on Claude Code that enhances AI capabilities with specialized agents, intelligent search, and comprehensive research workflows.

## 🚀 Overview

This repository extends Claude Code's native capabilities through custom agents and MCP (Model Context Protocol) integrations, focusing on automated research, data analysis, and knowledge synthesis. The system enables sophisticated multi-hop reasoning, parallel execution, and evidence-based research workflows.

## ✨ Key Features

### 🔍 Deep Research System
- **Adaptive Planning**: Intelligent research planning with multiple strategies
- **Multi-Hop Reasoning**: Complex investigation across multiple information layers
- **Evidence Management**: Automated source verification and credibility assessment
- **Parallel Execution**: Optimized research workflows with concurrent operations

### 🛠️ MCP Integrations
- **Tavily Search**: Advanced web search with content extraction
- **Sequential Thinking**: Multi-step reasoning and analysis
- **Custom Agents**: Specialized research and analysis capabilities

### 📊 Research Outputs
- Structured reports with confidence scoring
- Automated documentation and knowledge synthesis
- Real-time research tracking and validation

## 🏗️ Architecture

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│  Claude Code    │    │  MCP Servers    │    │  Custom Agents  │
│  Base Platform  │◄──►│  (Tavily, Seq)  │◄──►│  & Commands     │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         │                       │                       │
         ▼                       ▼                       ▼
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Configuration │    │   Web Search    │    │   Research      │
│   & Permissions │    │   & Analysis    │    │   Workflows     │
└─────────────────┘    └─────────────────┘    └─────────────────┘
                                                               │
                                                               ▼
                                                    ┌─────────────────┐
                                                    │   Research      │
                                                    │   Reports       │
                                                    │   (claudedocs/)  │
                                                    └─────────────────┘
```

## 📦 Installation & Setup

### Prerequisites
- Claude Code access (claude.ai/code)
- Node.js (for MCP servers)
- API keys for external services (as needed)

### Configuration

1. **Clone or setup the repository**
   ```bash
   # Ensure the repository structure matches the Claude Code requirements
   ```

2. **Configure MCP Servers**
   The `.mcp.json` file configures the available MCP servers:
   ```json
   {
     "mcpServers": {
       "sequential-thinking": {
         "type": "stdio",
         "command": "npx",
         "args": ["-y", "@modelcontextprotocol/server-sequential-thinking"]
       },
       "tavily": {
          "type": "stdio",
          "command": "npx",
          "args": ["-y", "tavily-mcp@latest"],
          "env": {
            "TAVILY_API_KEY": "your_tavily_api_key_here"
          }
        }
      }
  }
   ```

3. **Set Permissions**
   The `.claude/settings.local.json` file controls tool permissions:
   ```json
   {
     "permissions": {
       "allow": [
         "WebSearch",
         "Bash(npx:*)",
         "mcp__tavily__tavily-search",
         "mcp__sequential-thinking__sequentialthinking"
       ]
     }
   }
   ```

## 🚀 Usage

### Basic Research Command

```bash
/research "your research query here"
```

### Advanced Research Options

```bash
# Specify research depth
/research "quantum computing developments" --depth deep

# Choose planning strategy
/research "AI safety frameworks" --strategy unified

# Combined options
/research "competitive analysis" --depth exhaustive --strategy planning
```

### Available Parameters

- **`--depth`**: Research depth level
  - `quick`: Basic search, 1 hop, summary output
  - `standard`: Extended search, 2-3 hops, structured report
  - `deep`: Comprehensive search, 3-4 hops, detailed analysis
  - `exhaustive`: Maximum depth, 5 hops, complete investigation

- **`--strategy`**: Planning approach
  - `planning`: Direct execution with minimal clarification
  - `intent`: Interactive clarification before execution
  - `unified`: Balanced approach with user feedback

## 📁 Project Structure

```
custom-claude/
├── .claude/                          # Claude Code configuration
│   ├── agents/                       # Custom agent definitions
│   │   └── deep-research-agent.md    # Deep research agent
│   ├── commands/                     # Custom commands
│   │   └── research.md               # Research command implementation
│   ├── MODE_DeepResearch.md          # Research mindset configuration
│   ├── RESEARCH_CONFIG.md            # Research system configuration
│   ├── MCP_Tavily.md                 # Tavily MCP server documentation
│   ├── MCP_Sequential.md             # Sequential thinking MCP documentation
│   ├── settings.local.json           # Permission settings
│   └── Claude.md                     # Minimal configuration file
├── claudedocs/                       # Research outputs
│   ├── research_*_*.md              # Generated research reports with timestamps
├── .mcp.json                        # MCP server configuration
├── package.json                     # Dependencies (tavily-mcp)
└── README.md                        # This file
```

## 🔧 Core Components

### Deep Research Agent
Located in `.claude/agents/deep-research-agent.md`, this agent handles:
- Complex research task decomposition
- Multi-hop reasoning and investigation
- Evidence synthesis and validation
- Confidence scoring and source verification

### Research Command
Located in `.claude/commands/research.md`, implements:
- Research workflow orchestration
- Parallel execution optimization
- Todo-based progress tracking
- Structured report generation

### MCP Integrations
- **Tavily**: Web search, content extraction, real-time information
- **Sequential Thinking**: Complex reasoning, step-by-step analysis

## 📊 Research Capabilities

### Multi-Hop Reasoning Patterns
- **Entity Expansion**: Person → Affiliations → Related work
- **Temporal Progression**: Current → Recent → Historical context
- **Conceptual Deepening**: Overview → Details → Examples → Edge cases
- **Causal Chains**: Observation → Immediate cause → Root cause

### Evidence Management
- Source credibility assessment using tiered scoring system
- Information consistency verification across multiple sources
- Bias detection and mitigation strategies
- Explicit confidence levels in all research outputs

### Parallel Execution
The system optimizes for parallel operations:
- Batch search queries for efficiency
- Concurrent content extraction
- Independent analysis workflows
- Parallel tool execution when dependencies allow

## 📈 Example Outputs

Research outputs are saved to the `claudedocs/` directory with structured formats including:
- Executive summaries
- Methodology documentation
- Detailed findings with citations
- Confidence assessments
- Source references
- Actionable insights


## 🔐 Security & Privacy

### Data Handling
- No training on user data by external model providers
- Configurable data retention policies
- Zero Data Retention (ZDR) options available
- Transparent telemetry controls

### Access Controls
- Granular permission system through Claude Code
- Configurable MCP server access
- Tool-specific permission settings

## 🤝 Contributing

This project is designed as a configuration and extension system for Claude Code. Contributions should focus on:

1. **Agent Enhancements**: Improving research agents and workflows
2. **MCP Integrations**: Adding new MCP servers or enhancing existing ones
3. **Research Methods**: Expanding research capabilities and methodologies
4. **Documentation**: Improving configuration and usage documentation

## 📝 Development Notes

- This is a configuration-only repository (no traditional source code)
- Built on Claude Code's extension system
- Uses MCP for external service integrations
- Outputs are structured markdown documents
- No build system or testing framework required

## 🛠️ Troubleshooting

### Common Issues

1. **MCP Server Connection Issues**
   - Verify Node.js installation
   - Check MCP server configuration in `.mcp.json`
   - Ensure network connectivity for external services

2. **Permission Errors**
   - Review `.claude/settings.local.json`
   - Ensure required tools are in the allow list
   - Check Claude Code's permission system

3. **Research Command Not Found**
   - Verify command file exists in `.claude/commands/`
   - Check Claude Code's command loading
   - Review command syntax and formatting

## 📄 License

This project is configured based on the [super-claude](https://github.com/SuperClaude-Org/SuperClaude_Framework) which is used MIT License.  

## 🔗 Related Resources

- [Claude Code Documentation](https://docs.claude.com/en/docs/claude-code/overview)
- [MCP Specification](https://modelcontextprotocol.io/)
- [Tavily Search API](https://tavily.com/)
- [Sequential Thinking MCP](https://github.com/modelcontextprotocol/server-sequential-thinking)

---

**Note**: This repository represents a sophisticated research automation system built on Claude Code. It's designed for researchers, analysts, and knowledge workers who require comprehensive, evidence-based research capabilities with AI assistance.