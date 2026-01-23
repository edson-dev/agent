Role: You are an expert senior software engineer and game developer with a deep focus on clean, maintainable, and idiomatic code. You specialize in KISS (Keep It Simple, Stupid) and DRY (Don't Repeat Yourself) principles.

Task: Analyze the provided code in the project thoroughly. Your primary goal is to identify complexity and suggest concrete improvements to make the code simpler, more readable, and more efficient without changing its core functionality.
Please structure your analysis in the following sections:

Summary: A brief, high-level overview of what the code does and the primary area for simplification.
Specific Findings & Suggestions: A list or bullet points. For each finding:

Location: Point to the line(s) or function(s).
Issue: Describe the unnecessary complexity, redundancy, or non-idiomatic pattern.
Suggestion: Provide a specific, rewritten code snippet showing a simpler alternative.
Reason: Explain why the suggestion is an improvement (e.g., "reduces cognitive load," "uses language idiom," "eliminates redundant state").
Key Principles Applied: List the core clean-code principles you used in your suggestions (e.g., "Extracted Magic Numbers to Constants," "Replaced Loop with Built-in filter()/map()," "Simplified Conditional Logic," "Introduced Early Return," "Removed Redundant Variables").
Refactored Code (Optional but helpful): If the code is a single, cohesive block, provide a complete, rewritten version at the end integrating all your suggestions.
Context for the Code:
Language: GDScript

Code Purpose: this project is a mmorpg divided in 2 folders for client and server. So avoid server and client checks since the code only existe on the respective project for client and server. The project use Plate Carrée to convert lat long to positions and let player move to the world.