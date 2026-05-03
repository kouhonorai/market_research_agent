# Market Research Agent for Student Budgeting App

## Project Overview
This project is based on CrewAI and modifies the original research + write demo into a practical market research application for a Student Budgeting App.

The new application focuses on a real business scenario: a **Student Budgeting App**.  
The system takes a product name as input and generates:
- user personas,
- competitor analysis,
- market opportunities,
- and a final market research report.

This project demonstrates how a general CrewAI demo can be transformed into a more practical multi-agent workflow for a specific product and market research use case.

## Input
**Product / project name**

Current test input:
- `Student Budgeting App`

## Output
The system generates:
- User personas
- Competitor analysis
- Market opportunities
- Final market research report

The final report is saved as:
- `report.md`

## Modified Parts from the Original Demo
Compared with the original CrewAI research + write demo, the following modifications were made:

1. The input variable in `main.py` was changed from `topic` to `product`.
2. The original generic agents were replaced with three customised agents:
   - `user_researcher`
   - `competitor_analyst`
   - `report_writer`
3. The original tasks were replaced with three customised tasks:
   - `user_research_task`
   - `competitor_analysis_task`
   - `final_report_task`
4. The workflow was redesigned for a real-world market research scenario instead of a general topic-based demo.
5. The project topic was set to **Student Budgeting App**.
6. The model configuration was updated to run with Gemini.

## Project Structure
```
market_research_agent/
├── .env
├── pyproject.toml
├── report.md
└── src/
    └── market_research_agent/
        ├── main.py
        ├── crew.py
        └── config/
            ├── agents.yaml
            └── tasks.yaml
```

## File Roles
- `main.py`: defines the input and starts the crew execution
- `crew.py`: assembles the agents and tasks into a sequential workflow
- `agents.yaml`: defines agent roles, goals, and backstories
- `tasks.yaml`: defines task descriptions, expected outputs, and agent-task assignments


## Execution Flow
Step 1: Receive product input  

Step 2: User Research Agent analyses target student users, financial needs, spending habits, pain points, and use 
cases  

Step 3: Competitor Analysis Agent analyses major competitors, their strengths, weaknesses, and market gaps  

Step 4: Report Writer Agent combines the research findings into a final structured market research report  

Step 5: Output the final market research report and save it as `report.md`


## Agents

### 1. User Research Agent
This agent is responsible for identifying target student users, their financial needs, spending habits, pain points, and common use cases.

### 2. Competitor Analysis Agent
This agent is responsible for analysing major competitors, their key features, strengths, weaknesses, and possible market gaps.

### 3. Report Writer Agent
This agent is responsible for combining the previous research results into a final structured market research report.


## Tasks

### 1. User Research Task
This task produces a structured user research summary, including target users, user personas, financial needs, spending habits, pain points, and common use cases.

### 2. Competitor Analysis Task
This task produces a structured competitor analysis, including major competitors, their key features, strengths, weaknesses, and possible market opportunities.

### 3. Final Report Task
This task produces a complete market research report in markdown format based on the previous two tasks.


## How to Run

### 1. Install dependencies
```bash
uv sync
```

### 2. Configure environment variables
```env
MODEL=gemini/gemini-2.5-flash-lite
GOOGLE_API_KEY=your_api_key
```

### 3. Run the project
```bash
crewai run
```

## Example Result
The customised project was successfully executed with the test input **Student Budgeting App**.

The final output includes:
- detailed user personas,
- competitor analysis of budgeting and finance apps,
- identified market gaps,
- and final recommendations.

The generated result is saved in:
- `report.md`


## Key Learning
This project shows that the original CrewAI demo can be transformed into a more realistic business workflow by:
- redesigning the agent roles,
- redefining the tasks,
- changing the input structure,
- and aligning the overall workflow with a real product scenario.

It also demonstrates how a multi-agent framework can be adapted to practical market research tasks.