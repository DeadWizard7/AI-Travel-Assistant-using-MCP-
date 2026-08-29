# AI Travel Assistant with MCP

An AI-powered Travel Assistant built with **n8n, Google Gemini, and Model Context Protocol (MCP)**.

The assistant helps users plan trips by providing personalized recommendations using live travel information such as weather, attractions, hotels, restaurants, coordinates, and currency exchange rates.

---

## Project Preview

### AI Travel Assistant

![AI Travel Assistant](AI%20Travel%20Assistant..png)

### MCP Travel Tools Main Server

![MCP Travel Tools Main Server](MCP%20Travel%20Tools%20Main%20Server.png)

---

##  Project Overview

This project combines an AI Agent with an MCP server to create a practical travel planning assistant.

The user can simply ask questions such as:

> "Plan a 3-day trip to Cox's Bazar."

The AI Travel Assistant processes the request and uses MCP tools to collect real-world travel information.

The final response can include:

- 🌤️ Weather information
- 🏖️ Tourist attractions
- 🏨 Hotels and guest houses
- 🍽️ Restaurants and cafes
- 📍 Location coordinates
- 💱 Currency exchange rates
- 💾 Saved user preferences

The MCP server provides six reusable travel tools that the AI agent can call when required.

---

## Why MCP?

A normal AI model depends mainly on its training knowledge.

However, travel information changes frequently.

For example:

- Weather changes every day
- Hotel information can change
- Restaurant locations can change
- Exchange rates change frequently
- New attractions and places can appear

To solve this problem, this project uses **Model Context Protocol (MCP)**.

The MCP server provides live tools that the AI agent can use to retrieve real-world information instead of depending only on static knowledge.

The MCP server is built in **n8n** using the **MCP Server Trigger** node and is connected to the AI Travel Assistant using the **MCP Client Tool** node.

---

## System Architecture

The project contains two main n8n workflows:

### 1. AI Travel Assistant

The main AI workflow contains:

- When Chat Message Received
- AI Travel Agent
- Google Gemini Chat Model
- Conversation Memory
- MCP Client
- Get User Preferences
- Save User Preference

The user sends a travel request to the AI agent.

The agent understands the request and decides which MCP tools are required.

---

### 2. MCP Travel Tools Main Server

The MCP server contains six travel tools:

```text
MCP Server Trigger
        |
        +---- Get Coordinates
        |
        +---- Get Weather
        |
        +---- Get Attractions
        |
        +---- Get Hotels
        |
        +---- Get Restaurants
        |
        +---- Get Exchange Rate
