# AIStoryMapper
This project was created to support Technical Program Managers (TPMs), Product Owners, and Engineers in accelerating the gap between customer feedback and actionable engineering work.

## Table of Contents

- [Overview](#overview)  
- [Prerequisites](#prerequisites)  
- [Installation](#installation) 
- [Features](#features) 
- [Use Cases](#use-cases)
- [Usage](#usage)
- [Future Improvements](#future-improvements)

## Overview
**AIStoryMapper** is a developer productivity tool that extracts structured Agile work items — including user stories and spikes — directly from meeting transcripts or project notes.

Powered by **GitHub Copilot Chat (GHC)**, this tool supports two usage modes:

- **Custom Agent Mode** (for VS Code Insiders with agent support)
- **Prompt-based Mode** (for all other users via GitHub Copilot Chat)


## Prerequisites
- Visucal Studio Code OR Visual Studio Code Insiders
- GitHub Copilot extension:
    - Make sure you have a GitHub Copilot license or subscription.
    - Install and enable the GitHub Copilot extension from the VS Code Marketplace.
    - GitHub Copilot Chat enabled in **VS Code**
    - For agent mode: **VS Code Insiders** with **Custom Copilot Agent (Preview)** support
- A transcript or note file, e.g., `AIStoryMapper/transcripts/yourfile.txt`


## Installation
1. Clone the Repository

```bash
git clone https://github.com/UrjaSoni/AIStoryMapper

cd AIStoryMapper
```
1. Open in VS Code

- Launch Visual Studio Code and open this repository’s folder.


## Features

- Extracts detailed, ready-for-refinement Agile stories and spikes
- Parses raw transcripts and maps conversation into actionable work
- Supports metadata tagging (e.g., UX, DevX, AI, Reporting, etc.)
- Flags vague or unclear areas as `refinement` and marks complete items as `ready`
- Output is structured in markdown format and can be saved as a story map document


## Use Cases

- Turn customer calls, discovery sessions, or brainstorm notes into backlog items
- Rapidly generate user stories, acceptance criteria, clarifying questions, and tags
- Standardize documentation for handoff to engineering teams


## Usage

### Option 1: Run with Custom Agent (VS Code Insiders Preview)
If you're using VS Code Insiders and have access to GitHub Copilot Custom Agents, follow these steps:

1. Open the transcript or notes file
Open the `.txt` file you'd like to extract user stories from (e.g., AIStoryMapper/transcripts/contoso_mock_meeting_transcript.txt)

1. Open Copilot Chat
Open the Copilot Chat pane from the sidebar (or press Cmd+I / Ctrl+I if you have the shortcut enabled).

1. Choose Your Custom Agent

Click the dropdown in the upper-right of the Copilot Chat window (next to the "Send" button).

Select the userstories Agent from the list of available agents.

- Ask it:

    `Please extract user stories and spikes from this transcript file.`

1. Output
The agent will:

- Parse the content

- Generate structured user stories and spikes

- Include full metadata, tags, status (ready or refinement)

- Output the results as a markdown document you can save

1. Save
If you like the changes the GitHub Copilot made, you can click on 'Keep' button to save the changes.

###  Option 2: Prompt-Based (GitHub Copilot Chat – Standard VS Code)

If you do not have access to Custom Agent Mode, you can use GitHub Copilot Chat directly:

1. Open your transcript file (e.g., AIStoryMapper/transcripts/contoso_mock_meeting_transcript.txt)

2. In Copilot Chat, paste the following prompt:

```
Please extract well-structured user stories and spikes from the currently open transcript file.

At the very top of your output, add this metadata block:

# User Stories and Spikes - Contoso Integration Review  
**Generated from:** [transcript or note file name] 
**Date:** [date the document is generated]  
**Total Items:** [count of all user stories + spikes]  

For each story or spike, include:  
- Title  
- User persona  
- Goal (I want to...)  
- Description  
- Acceptance criteria  
- Tags  
- Clarifying questions/gaps  
- Status (Ready or Refinement)

Format the output as a numbered markdown list.

Create all relevant items needed to fully cover the content of the transcript.

Provide the output as if you are creating a new standalone markdown document that can be saved uniquely each time (e.g., user-stories-YYYYMMDD-HHMMSS.md).

Do not add anything outside this format.

```

## Future Improvements
Shell script or CLI for auto-parsing and saving markdown output

GitHub Action to extract stories from transcripts in PRs

Optional integration with Jira, Linear, or Azure DevOps