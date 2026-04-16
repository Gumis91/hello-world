# Github Copilot setup prompts

## Vanilla feature request

Setup:

- new conversation
- plan agent
- Sonnet 4.6 model

> Add page on which I can take picture from my laptop's camera. I need to be able to take one or more pictures, and then download them to my computer. The page should be simple and easy to use, with a clear button to take the picture and a clear button to download the pictures.

Note: Switch to agent to enable file save

> Save it to vanilla-plan.md file in my workspace

## Setup phase 1: instruction

### MCP query for Agent instruction

Setup:

- MCP installed from json

> "awesome-copilot": {
      "command": "podman",
      "args": [
        "run",
        "-i",
        "--rm",
        "ghcr.io/microsoft/mcp-dotnet-samples/awesome-copilot:latest"
      ],
      "type": "stdio"
    }

- new conversation
- agent mode
- auto
- awesome-copilot tool enabled

> I'm planning to build my own custom agent using Github Copilot Agents. Using awesome-copilot MCP, find me best custom instructions for this task. List files with brief summary of its content.

> Install instructions.instructions.md, agents.instructions.md and agent-skills.instructions.md in user's .copilot folder.

## Setup phase 2: skills

### MCP query for Suggest Awesome Github Copilot Agents skill

Setup:

- new conversation
- agent mode
- auto
- awesome-copilot tool enabled

> Do you have any good skill in awesome-copilot that can be used to assist in selecting best custom skills from this MCP?

> Install suggest-awesome-github-copilot-skills  in user's .copilot folder

### MCP query for Specification skill

> find me a skill that will help me in building specification for my feature

> yes, install create specification

### MCP query for TlDr and Web Coder skill

> I need something for TlDr'ing long documents and something for web coding - both should be skills. Suggest 5 best for each category

> Install tldr-prompt, web-coder and premium-frontend-ui

## Replay feature request, with skills

Setup:

- new conversation
- agent mode
- Sonnet 4.6 model

> /create-specification Add page on which I can take picture from my laptop's camera. I need to be able to take one or more pictures, and then download them to my computer. The page should be simple and easy to use, with a clear button to take the picture and a clear button to download the pictures.

## Setup phase 3: agents

### MCP query for agents

Setup:

- new conversation
- agent mode
- auto
- awesome-copilot tool enabled

> I need agents that will help me challenge my ideas and convert specification into something ready for implementation - give me best matches from awesome-copilot, but don't install yet

> Install Devils Advocate and Implementation Plan Generation Mode in user's .copilot folder

> How about some implementation orchestrator? I do have my specification ready - I need to focus on implementing it using orchestrator and subagents.

## Specification refinement

### devils advocate on specification

Setup:

- new conversation
- Devil's advocate
- auto
- add specs to chat

> challenge attached specs

Setup: 

- add Angular docs MCP
> "angular-docs": {
      "command": "npx",
      "args": [
        "angular-mcp-server"
      ],
      "disabled": false,
      "autoApprove": [],
      "type": "stdio"
    }

- make sure Angular MCP is enabled
- switch back to regular agent mode
- select Sonnet 4.6
- attach specs

> /create-specification take feedback from current session and apply it to specification. Cross check ideas with available Angular MCP servers

### Implementation plan generator mode on specification

Setup:

- same conversation
- Implementation Plan Generation Mode
- select Sonnet 4.6
- add specs to chat

> Create implementation plan out of this specification

## From chat to plugin

### Custom skill and agent out of pipeline: from specification to implementation plan, with devil's advocate, MCP servers and orchestration / subagents implementers

Setup:

- same conversation
- agent mode
- select Opus 4.6
- add specs to chat

> I've created attached specs using /create-specification skill. I then fed it into this conversation. Help me build custom skill out of it with accompanying agent. Reuse skills, agents and only focus on custom parts of the process.

### Build plugin and marketplace out of created skill and agent

Setup:

- add marketplace through UI: https://github.com/anthropics/claude-code
- install plugin-dev
- show README
- same conversation

> /plugin-dev:create-plugin Create plugin out of created skills and agents. Include external dependencies like used MCP servers, agents, skills and instructions

### Showcase Tl;Dr skill

Setup:

- new conversation
- agent mode
- auto
- awesome-copilot tool enabled

> /tldr-prompt what's in plugin-dev:create-plugin?
