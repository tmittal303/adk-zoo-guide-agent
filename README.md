# adk-zoo-guide-agent
The system runs as a coordinated multi-agent pipeline - each agent has a single, well-defined job, and they hand off to each other in sequence.

Agent 1 — Zoo Greeter
The entry point. It greets the user and asks what animal they want to learn about. When the user responds, it captures the input using add_prompt_to_state and immediately delegates to the tour_guide_workflow.

Agent 2 — Comprehensive Researcher
The brain of the pipeline. It reads the user's query, decides what sources it needs, and fetches data accordingly — pulling from Wikipedia via API for general knowledge, or combining multiple sources for more complex questions. It uses the model's native tool-calling to make these decisions dynamically.

Agent 3 — Response Formatter
The final voice. It takes the raw, potentially multi-source data from the researcher and shapes it into a single, cohesive response — presenting zoo-specific context first, followed by broader facts. This is the output the user actually sees.

