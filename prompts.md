# Github Copilot setup prompts

## Vanilla feature request

> Add page on which I can take picture from my laptop's camera. I need to be able to take one or more pictures, and then download them to my computer. The page should be simple and easy to use, with a clear button to take the picture and a clear button to download the pictures.

## Setup phase 1: instruction

### MCP query for Agent instruction

> I'm planning to build my own custom agent using Github Copilot Agents. Using awesome-copilot MCP, find me best custom instructions for this task. List files with brief summary of its content.

> Install agents.instructions.md in for my user.

> How about skills?

## Setup phase 2: skills

### MCP query for Suggest Awesome Github Copilot Agents skill

> Do you have any good skill in awesome-copilot that can be used to assist in selecting best custom skills from this MCP?

> Install suggest-awesome-github-copilot-skills for my user

### MCP query for Specification skill

> find me a skill that will help me in building specification for my feature

> yes, install create specification

### MCP query for TlDr and Web Coder skill

> I need something for TlDr'ing long documents and something for web coding - both should be skills. Suggest 5 best for each category

### MCP query for Web Coder skill

> what about this? https://github.com/github/awesome-copilot/tree/main/skills/web-coder

## Replay feature request, with skills

> /create-specification Add page on which I can take picture from my laptop's camera. I need to be able to take one or more pictures, and then download them to my computer. The page should be simple and easy to use, with a clear button to take the picture and a clear button to download the pictures.

### Showcase Tl;Dr skill

> /tldr-prompt what's in agent-skills.instructions.md?

## Setup phase 3: agents

### MCP query for Agent 1: Devils Advocate
### MCP query for Agent 2: Implementation plan generator mode
### MCP query for Agent 3: Repeat until good (RUG)

> I need following agents: Devils Advocate, Implementation plan generator mode and RUG - give me best matches from awesome-copilot, but don't install yet

## Specification refinement

### devils advocate on specification

> /create-specification take feedback from current session and apply it to specification

### Implementation plan generator mode on specification

## Custom skill out of pipeline: from specification to implementation plan

## Custom agent out of pipeline: from specification to implementation plan, with devil's advocate and RUG agents in the loop

## Implement feature X

