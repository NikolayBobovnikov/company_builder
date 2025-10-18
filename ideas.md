# AI Agent Company: Unstructured Thoughts

## Core Concept: AI-Powered Autonomous Company

Let's brainstorm the idea for a project. I want to orchestrate AI agents into somewhat like a company. A normal company is a bunch of people which group together to create a product or service. Inside the company, the process of creating that product/service is divided into smaller stages, so that big task is decomposed. Different departments are responsible for different stages or parts of the work. People in each department are responsible for their smaller part of the work.

## Particle-Based Work Model

I heard the metaphor of 'particles' - all processes can be viewed as streams of 'particles', the atomic unit of work is to get particles which goes into the input, then do some work (transform particles or create new ones) and put the resultant particles to the output. 

For instance, for a customer support department, the input particle for a worker would be an incoming call/request, and the output particle would be the document with description of the use case, failure mode, or feature request, or something. And this document is then routed as a new particle to some other particle processing unit higher on the hierarchy of the company.

Each processing unit (department, working group, single person in the company) works exactly which particles he is working with, and what is the output of its work. Some call that a 'role description', or a 'guideline'. Name doesn't matter (though we would probably need to choose one, for our glossary and domain model).

## The AI Agent Era

Now, we are entering to a new era of AI agents, which can process some particles instead of people. But they might need a special handling, to organise their work and incorporate into a company's processes.

All of that needs to be taken into account, when designing new type of the company I aim to create - the fully autonomous company where AI agents are working together to produce a product or service.

## AI Agent Challenges

Some of the things specific to AI agents which I heard of, which needs to be taken into account:

- **Hallucination**: Text models generate the output, and during generation may produce 'made up' facts which may be incorrect and not be grounded on the reality
- **Over engineering**: Tendency to produce complex output, when much simpler output of the same quality (solving the same problem) exists
- **Eternal loops**: Some start producing same output again and again, without stopping. In mathematics, there is a thing called a 'sequence', and this problem is that particle sequence does not converge
- **Not adhering to the rules**: That may be role descriptions, checklists, TODO items, etc

## Development Approach

I am a developer myself, but not a high level one. So I will be working on this project myself, starting from the basics and building from the ground up, adding features one by one, and increasing complexity gradually. I am going to prototype in Python.

## System Architecture Components

Now, I foresee the system to be consisting of the following parts:

- **Normal software services**: Dedicated, running as RPC or REST web servers, doing work at the request
- **Raw requests to AI model providers**: At this moment, those can produce text or images at the request. These are not deterministic (that is the feature!), and can produce 'tool calls' - JSON/XML/other encoded objects wrapping a normal RPC request in the above
- **CLI agents**: At this moment, those are running in the terminal, and can be instructed to do some more complex task in there. Internally, they are using raw requests to AI models like the above, but also incorporate complex logic for orchestrating requests/responses, trying to achieve the goal of completing the task which the agent is instructed for. There is a known nuance here: sometimes CLI agent turns into interactive mode, and ask for permission or making a choice from several options. So, to work with CLI agent, I need a 'CLI agent manager' or something, which would give CLI agent a permission or make a decision
- **Virtual environments**: This is a crucial part here, as all the work produced by AI agents would need to be happening in some environment - a virtual machine, docker container, windows powershell, linux shell, ssh access, or visual environment with screen, or some entirely different stuff. And work done on one project/task, should be isolated from the work done on other project/task, so that not to accidentally damage one while working on another. For that, I will need a virtual environment management system/service

## Agent Specialization

Now, AI agent in general (and CLI agent in particular) is a general-purpose proactive 'agent' (sorry for a tautology), which is an equivalent of a 'generic human'. Now, the company does not hire 'generic humans' - it hire programmers, QA specialists, architects, accountants, lawyers, you name it. 

I think that is related to both human abilities (programmers normally cannot do work of the lawyer as good as lawyer can, and vice versa), and internal company structure - which divides the overall flow of particles of all kind and organize them into complex system, where different 'particle processor' types (i.e. specializations) arise. So, like the human needs a specialization, so does an AI agent.

## Company Process Definition

Now let's discuss one of the goals of this project, in particular defining a company. From my standpoint, the company is defined by the "particle flow design": departments, activities, data/document/artifact/money flows, role definitions, etc. And this all is needed and influenced by the products and services the company produces. 

And here is what comes to my mind when speaking of this: BPMN diagrams. Maybe something else can be applicable here, if so please let me know, we will discuss it as well.

## Process Automation

So, eventually we decide on some formal description/definition of the inner company's processes. Now, I want to implement its automation. There may be some projects for that (like automation and execution of BPMN) which solves it for some parts. And I will probably need to implement the remaining parts.