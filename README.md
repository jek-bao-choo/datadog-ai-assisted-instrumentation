# Inspiration
This project is inspired by a discussion with Nuttee and through my observation of area for improvement of onboarding experiences.

# Disclaimer
This project is unofficial and not endorsed by Datadog.

# Problem Statement
The objective of this project is to reduce friction and time-to-value when prospects evaluate Datadog during a PoC, with a specific focus on agent and SDK instrumentation. From a prospect’s perspective, onboarding friction often comes from unfamiliar instrumentation patterns and the cognitive load of navigating extensive documentation.

# My Writing: Prospects' Experience
I must assume that the Datadog users don't have Claude Code, OpenCode, Codex, Cursor, or other similar AI coding tools (but would have internet access). If she has one of the mainstream coding tools, then she would be importing the SKILLS (or Datadog Onboarding MCP Server) and the relevant Claude Code's commands. If she doesn't have one of the mainstream coding tools, then she needs a portable (NO INSTALLATION) and light-weight AI coding tool that works with Windows, Mac, and Linux like Claude Code or OpenCode. Additionally, she would need access to a LLM model. So for a start of this project, I could provide my own OpenRouter API Key at my own expense. But to keep cost sustainable, I am considering using llama.cpp (portable with no installation) for this project.  

# My Writing: Considerations
To get the instrumentation context, one can use Datadog Onboarding MCP Server or a Claude Code SKILLS that offers content on Datadog Docs (the latter is currently unavailable so I need to build it). But why think about building something if Datadog Onboarding MCP Server is currently available?

So using SKILLS is similar to using Datadog Docs through Datadog MCP Sever. Alternatively, using SKILLS is similar to using Datadog Public Website Doc via Claude Code internet search. 

So what is the value of using SKILLS for content from Datadog Docs to instrument (instead of using Datadog Docs via Internet search or Datadog MCP Server)? Also can't we just use Datadog Github Docs repo https://github.com/DataDog/documentation/blob/master/content for instrumentation instead? 

To answer this loaded question:

1. Using the Datadog MCP Server requires authentication from Datadog using Datadog account. For me that is a blackbox right now. https://app.datadoghq.com/rum/list/create-agentic and the MCP Sever URL is https://mcp.datadoghq.com/api/unstable/mcp-server/mcp?toolsets=onboarding 

2. Though the Datadog GitHub Doc repo ttps://github.com/DataDog/documentation/blob/master/content represents the latest content, but in raw form it is too broad and inefficient for Claude Code consumption without additional structure like SKILLS. 

3. Using the Claude Code internet search, then it might require at least one internet hop to get to the Datadog Github Docs https://github.com/DataDog/documentation/blob/master/content which might not be efficiency and accurate. The accurate is key here. 

In summary - besides using the Datadog MCP Server unaddressed - using SKILLS referencing the content from Datadog Github Docs repo offers reliable efficiency and accuracy for developers instrumenting Datadog agents, SDKs, or both. Utimately, the objective of this project is to make adopting Datadog agents and SDKs onboarding easier and faster.

How about maintainiung of this project? It should be designed to be easy such that as the Datadog Docs get updated, it would be updated whenver it is updated. Then do we have to fork the Datadog Github Docs repo github.com/DataDog/documentation/blob/master/content  or can I just setup another repo with a custom code to crawl the Datadog Github Doc repo regularly? I prefer forking it but how do we maintain a folder called skills with several subfolders of skill names each with a SKILL.md in it while referencing the the latest content in github.com/DataDog/documentation/blob/master/content? TODO: Research how to do this.

## ChatGPT Writing: Maintenance Recommendation
The maintenance goal is eventual consistency with Datadog documentation rather than strict real-time parity. SKILLS should live in a separate repository and rely on automation to track relevant upstream documentation, update curated content when changes occur, and preserve SKILLS-specific structure and annotations. Forking the Datadog documentation repository is unnecessary and would introduce avoidable maintenance overhead, whereas automated extraction or referencing provides better long-term sustainability.

# ChatGPT Writing: Why SKILLS Instead of the MCP Server
SKILLS do not replace the Datadog Onboarding MCP Server but provide a developer-controlled and transparent alternative that is more suitable for proof-of-concept tooling and experimentation. Unlike the MCP Server, SKILLS do not require Datadog authentication, do not operate as a black box, and can be inspected, extended, and adapted as part of an open workflow.

# ChatGPT Writing: Why SKILLS
SKILLS are not an alternative documentation source but a curated and structured interface over existing Datadog documentation. They transform raw documentation into scoped, opinionated knowledge aligned with onboarding and instrumentation workflows. By filtering irrelevant content, stabilizing prompts, and structuring guidance around concrete tasks, SKILLS reduce hallucination risk, improve token efficiency, and increase accuracy. The core value lies in this transformation layer, rather than in the underlying documentation itself.

# My Writing: Project Objective
The objective of this project is not to reinvent the wheel but to empower users to instrument Datadog agent and SDK onboarding easier and more approachable during PoC evaluations by providing AI-assisted instrumentation support through this project.


