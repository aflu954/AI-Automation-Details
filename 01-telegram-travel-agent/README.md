Build a Telegram Customer Support Agent in n8n

Scenario
You are working for a travel agency. Customers frequently message the company on Telegram asking about visa requirements, tour packages, office hours, pricing, and booking procedures.

The company wants an AI-powered Telegram agent that can instantly answer these common questions, reducing the workload on human support staff.

Objective
Build a simple Telegram AI agent in n8n that acts as a customer support representative.

Requirements

Create a Telegram bot and connect it to n8n.

Use a Telegram Trigger node to receive incoming messages.

Connect the trigger to an AI model.

Write a detailed system prompt that makes the AI behave like a professional customer support executive.

The AI should:

Answer customer questions politely and professionally.

Stay within the travel agency context.

Ask follow-up questions if customer information is missing.

Decline to answer unrelated questions and redirect the conversation back to travel services.

Send the AI's response back to the customer through Telegram.

Constraints
Keep the workflow simple.

Do not use databases, memory, APIs, or tools.

The entire behavior of the agent should be controlled through prompt engineering.

Deliverables
A working n8n workflow.

The system prompt you designed.

An exported workflow JSON.

Test the bot with at least five different customer queries and include the responses.

