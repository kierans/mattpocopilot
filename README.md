# mattpocopilot

An **in progress** port of Matt Pocock's skills for use with M365 Copilot; with some added extras.

## Why?

If you're reading this; chances are you've heard of [Matt Pocock's Skills][1]. You might use them in Claude or Codex.
If you're like me you can't start anything anymore without reaching for `/grill-me`

But what if you're in the [M365 Copilot (Copilot) ecosystem][2]? This is where a lot of office workers are. People who 
work in 
accounting, legal, retail and are have a lot of years and IP in Microsoft technologies. They value the [Enterprise 
Data Protection][3] that Microsoft offers tham and they want to use Copilot in apps like Word and Excel where these 
people already live.

How can they benefit from the power that Pocock's skills bring?

That's what this repo is for.

## How to use these skills

One of the major differences with Copilot is that it's not easy to use skills directly in a chat. This repo will contain
definitions for agents and instructions on how to create the agent in Copilot

Each pocock skill will contain a versioned copy of the skill from the pocock repo. Any changes necessary for Copilot 
will be called out in the skill.

Copilot specific skills will be in the `copilot` folder and are designed to help integrate 

## Supported skills

### Copilot

- **[m365-file-edit-prompt](./skills/copilot/m365-file-edit-prompt)**

### Productivity

- **[grilling](./skills/productivity/grilling/SKILL.md)**: Interview the user relentlessly about a plan, decision, or idea until every branch of the design tree is resolved.
- **[handoff*](./skills/productivity/handoff/SKILL.md)**: Compact the current conversation into a handoff document 
  so another agent can continue the work. This skill has been modified to work for non-technical people.

## Supported agents

- **[brainstormer](./agents/brainstormer/AGENT_BUILDER.md)**: combines **grilling** with **handoff**

[1]: https://github.com/mattpocock/skills
[2]: https://www.microsoft.com/en-au/microsoft-365-copilot/in-apps-for-work
[3]: https://learn.microsoft.com/sl-si/microsoft-365/copilot/enterprise-data-protection