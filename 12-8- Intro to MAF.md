

Introduction to MAF

- Opensource
- Easily integrated with Azure ie. Foundry especially to manage agent run time, thread management, and easily integrated with services directly in foundry that you create. Interact with the foundry SDK...
- Orchestration framework that provides prebuilt objects for creating and running agents, handling response types, handling events, handling threads, creating an acyclic graph, checkpointing, shared states, human in the loop and more I cant remember. 
- You could handle all this yourself and maybe use it for the agent creation, but the observability of traces provide you an in-built evaluation/debugging abstraction.
- Today, to get yall familiar with this, I'll only be discussing major/core components of the library. We won't be covering shared state/thread management/azure integration/HITL/conversationstores/Middleware etc. Although if yall are interested, I can prepare that for a future workthrough. Along with the final solution I build for Sunset foods.
-

Core components:

- Agents/LLM clients
	- Any provider can be built here (abstractions from MAF provided, if not, you can use a respective providers SDK to integrate.)
- Executors
	- Class based vs Decorator
	- Agent as executor is fine too (dont reccomend as ive learnt it.)
- Workflows
	1. **Direct Edges**: Simple one-to-one connections between executors
	2. **Conditional Edges**: Edges with conditions that determine when messages should flow
	3. **Fan-out Edges**: One executor sending messages to multiple targets
	4. **Fan-in Edges**: Multiple executors sending messages to a single target
	5. Workflows as agents or workflows as tools. 
- DevUI
