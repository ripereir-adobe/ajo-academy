[home](README.md)

**AGENTIC EXERCISE**

<p align="center">
<img width="800" src="https://github.com/user-attachments/assets/9c94e953-ab53-4ff6-b4f2-c6e5ea244489" />
</p>

In this chapter of the lab, we are going to play with a simple Agentic use case. AI agents, powered by the Adobe Experience Platform Agent Orchestrator, are available to automate, optimize, and accelerate work inside Adobe Journey Optimizer (AJO). These agents can design journeys, analyze performance, optimize campaigns, manage audiences, and coordinate multi-step marketing actions—all through intelligent, autonomous behavior rather than manual configuration.

This includes agents such as:

- Journey Agent – Helps design and optimize customer journeys in AJO using natural language and autonomous decision-making
- Audience Agent – Builds and improves audience segments used in AJO
- Experimentation Agent – Suggests journey optimizations and experiments.

All these agents are coordinated by Adobe’s Agent Orchestrator, which provides the reasoning engine that allows them to act autonomously, make decisions, and work across Adobe Experience Cloud applications—including AJO.

In this exercise, let's use AJO agents to create a journey that starts with an Audience Qualification and delivers 2 promotional communications, one email and one push notification depending on the preferred channel or Customer consenting.



# Agentic Use Case

To start playing this use case, you have to access "**Ai Assistant**", this is possible either AEP Sandbox home page, or through AJO interface. The "Ai Assistant" is your interface UI, your prompt, where all interaction with Agent Orchestrator starts. Then Agent Orchestrator will decide which agents to call based on your text prompt requests.

  
  <img width="800" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Ai_Assistant_HomePage2.png" />
  
  <img width="700" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Ai Assistant_AJO.png" />  <img width="300" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Ai Assistant_AJO_Prompt.png" />

- Before starting interacting with Ai Assistant, please be sure you set your context as per the screenshot below:

  <img width="800" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Ai Assistant_SetContext.png" />


- Let's start building our journey with the creation of an audience, for that, let's use Ai Assistant prompt and copy/paste the following text/request to AEP Agent Orchestrator: "_I want to create an audience with profiles which propensity score is higher than 50_" (you can obviouly use your own text and native language if you prefer). Through the Ai Assistant, the agent orchestrator is calling the Audience Agent.


  <img width="700" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Ai Assistant_AudienceAgent.png" />


- You will then follow the next steps by answering "Yes" to the agent. You might need to review and approve/create.


- Then we'll create the Journey. Just use the following text in the prompt or create your own text: "_Can you help me building a Customer Journey starting with an Audience Qualification and sending an email and a push notification?_". Once again, through the Ai Assistant, the agent orchestrator is calling the Journey Agent.


  <img width="700" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Ai Assistant_JourneyAgent.png" />


- You will then follow the next steps by answering "Yes" to the agent. You might need to review and approve/create.
  
  

[Home](README.md)

