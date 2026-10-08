AI Travel Assistant Using MCP in n8n
🎯 Objective
Build an AI-powered Travel Assistant in n8n that uses the Model Context Protocol (MCP) to access external tools and provide accurate, real-time travel information.

📌 Scenario
A user wants to plan a trip. Instead of relying only on the AI model's built-in knowledge, the AI Agent should use MCP tools to retrieve live travel-related information before generating a response.

The AI Travel Assistant should analyze the retrieved information and provide a clear, helpful, and personalized travel recommendation.

Requirements
Your workflow must include the following:

1. Accept User Travel Query
The workflow should accept a travel-related query from the user.

Example:

"I want to visit Cox's Bazar this weekend."

2. Connect AI Agent with MCP
Connect an AI Agent in n8n to one or more MCP Servers.

The AI Agent should be able to identify which MCP tools are required based on the user's query.

3. Use MCP Tools
The AI Agent should use MCP tools to retrieve relevant, real-time information such as:

 Current weather conditions

Hotel availability

Tourist attractions

 Local restaurants

Currency exchange rates for international destinations

 Transportation information, if available

4. Analyze Retrieved Information
The AI Agent should analyze and combine the information retrieved from the MCP tools.

It should consider the user's requirements, destination, travel dates, budget, and preferences when generating the recommendation.

5. Generate Travel Recommendation
The AI Agent should generate a clear, useful, and personalized travel recommendation based on the retrieved information.

The response may include:

Recommended travel dates

Weather conditions

Hotel suggestions

Places to visit

Restaurant suggestions

Estimated travel considerations

Packing recommendations

Other useful travel tips

6. Return Final Response
The final travel recommendation should be returned to the user through the n8n workflow.

💬 Example User Queries
The workflow should be able to handle queries such as:

"Plan a 3-day trip to Cox's Bazar."

"Is it a good time to visit Kathmandu next week?"

"Find hotels and restaurants near Sajek Valley."

"What should I pack for a trip to Bandarban tomorrow?"

 Deliverables
1. n8n Workflow
Submit the exported n8n workflow file (.json).

The workflow should contain:

User input

AI Agent

MCP connection

MCP tools

Information retrieval

AI analysis

Final response

2. Execution Screenshot
Submit a screenshot showing a successful workflow execution in n8n.

The screenshot should clearly show that:

The workflow executed successfully

The AI Agent was triggered

MCP tools were used

A final travel recommendation was generated

3. MCP Server Information
Provide information about all MCP Servers used in the project.

For each MCP Server, mention:

MCP Server Name

Purpose

Tools provided

What information each tool retrieves

Example Format
MCP ServerToolPurposeWeather MCP ServerWeather ToolRetrieves current weatherHotel MCP ServerHotel SearchFinds available hotelsPlaces MCP ServerPlaces SearchFinds tourist attractionsRestaurant MCP ServerRestaurant SearchFinds nearby restaurants

4. Project Explanation
Write a 200–300 word explanation of your project.

Your explanation must include:

A. Why MCP was used
Explain why MCP was necessary instead of relying only on the AI model's built-in knowledge.

B. MCP Tools Used
Mention which MCP tools were called by the AI Agent and what each tool was used for.

C. Benefits of MCP
Explain how MCP improved the:

Accuracy of travel information

Real-time information retrieval

Usefulness of recommendations

Personalization of the final response

D. Challenges and Solutions (Optional)
Mention any challenges you faced while building the workflow and explain how you solved them.

Bonus Challenge: Add Memory
Implement Memory so that the AI Travel Assistant can remember the user's preferences and automatically use them in future travel recommendations.

The assistant can remember preferences such as:

 Preferred Budget: Budget / Mid-range / Luxury

 Favorite Hotel Type: Hotel / Resort / Hostel / Guesthouse

 Preferred Transportation: Bus / Train / Car / Flight

Dietary Preferences: Vegetarian / Halal / Other

Preferred Activities: Adventure / Relaxation / Sightseeing / Nature / Shopping

Example
If a user previously says:

"I prefer mid-range hotels and adventure activities."

The assistant should remember these preferences and use them when the user later asks:

"Plan a trip to Bandarban."

The AI Agent should automatically prioritize mid-range accommodation and adventure activities in its recommendation.

✅ Expected Workflow
User Query
↓
n8n Trigger
↓
AI Agent
↓
MCP Server(s)
↓
MCP Tools
↓
Real-Time Travel Data
↓
AI Agent Analysis
↓
Personalized Travel Recommendation
↓
Final Response to User

🎯 Final Goal
Build a working AI Travel Assistant in n8n that can understand a user's travel requirements, use MCP tools to retrieve real-time information, analyze the collected data, and provide an accurate and personalized travel recommendation.
