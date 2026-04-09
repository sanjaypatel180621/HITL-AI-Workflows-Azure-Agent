# HITL AI Workflows Azure Agent

![Implementing Enterprise Fraud Detection with Human-in-the-Loop AI](https://github.com/sanjaypatel180621/HITL-AI-Workflows-Azure-Agent/blob/main/Implementing%20Enterprise%20Fraud%20Detection%20with%20Human-in-the-Loop%20AI.PNG?raw=true)

This Human-in-the-Loop (HITL) AI Workflows with Azure Agent Framework which is explore the Contoso Fraud Detection & Response Workflow, where AI agents analyze suspicious activity and route high-risk actions to human analysts for review, using a real-time React + FastAPI dashboard for monitoring and interaction.


## 🔧 Environment Configuration

Create a `.env` file in the project root and add the following values:

### **Azure OpenAI Configuration**
```python
## Replace the value of AZURE_OPENAI_API_KEY and AZURE_OPENAI_ENDPOINT with the actual values
# Azure OpenAI Configuration
AZURE_OPENAI_API_KEY=----
AZURE_OPENAI_CHAT_DEPLOYMENT=gpt-4.1-mini
AZURE_OPENAI_ENDPOINT=https://agent----.openai.azure.com/
AZURE_OPENAI_API_VERSION=2024-10-01-preview

# MCP Server Configuration
MCP_SERVER_URI=http://localhost:8000/mcp

```

### Start All Services (3 terminals):

**Terminal 1 - MCP Server**
```python
cd mcp
uv run mcp_service.py
```

**Terminal 2 - FastAPI Backend:**
```python
cd agentic_ai/workflow/fraud_detection
uv run --prerelease allow backend.py
```

**Terminal 3 - React Frontend**
```python
cd agentic_ai/workflow/fraud_detection/ui
npm run dev
```

**Next to Launch the APP**
```text
ctrl + click on http://localhost:3000 to open the application in a browser
```

**View the Real-Time Workflow Visualizer UI**
![Implementing Enterprise Fraud Detection with Human-in-the-Loop AI](https://github.com/sanjaypatel180621/HITL-AI-Workflows-Azure-Agent/blob/main/Implementing%20Enterprise%20Fraud%20Detection%20with%20Human-in-the-Loop%20AI.PNG?raw=true)

**List of sample alerts from the Select Alerts drop-down:**
```text
Belew is the way to interact with Visualizer

1) Select Alert: from 3 sample alerts (ALERT-001, ALERT-002, ALERT-003)
Click on Start Workflow (2) to begin processing

2) Watch Live Updates: Nodes change color as executors run
🔵 Blue = Running
🟢 Green = Completed
⚪ Gray = Idle

3) Analyst Review: When high-risk fraud is detected, a review panel appears.

4) Submit Decision: Choose action and add notes
    Your Decision: If the severity is high, select Lock Account
    Analyst notes: Enter High risk confirmed from all three analyses.
    Immediate action: locking account to prevent unauthorized access.
      -> Select SUBMIT WORKFLOW

5) Monitor Events: The right panel shows the complete event stream.
```

Short Working Principle: This project is the **human-in-the-loop (HITL) workflow for fraud detection using the Azure Agent Framework**. You explored how AI agents analyze suspicious activity, route high-risk cases to human analysts, and interact with a real-time React + FastAPI dashboard to monitor workflow execution and submit decisions.
