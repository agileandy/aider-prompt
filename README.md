# Precision Prompting for AI Code Generation with Aider

This repository provides a structured approach to using the [aider](https://github.com/paul-gauthier/aider) AI coding assistant, called **Precision Prompting**.

Instead of relying on "vibe coding," Precision Prompting leverages a set of well-defined **Project Context files** to guide the Aider agent. This approach is inspired by established software development practices, as well the awesome [IndyDevDan](https://www.youtube.com/@indydevdan) Youtube channel. It aims to provide a more predictable, controlled, and efficient AI-assisted coding experience.

## **Key Principles of Precision Prompting:**

*   **Structured Project Context:**  Define the project's goals, architecture, technical environment, and current status in a set of Markdown files.
*   **Terms of Reference for the Agent:** Provide a clear "system prompt" (`.aiderCode.md`) outlining expected behavior, coding principles, and best practices for the AI agent to follow.
*   **Iterative Refinement:**  Continuously update and refine the Project Context files based on project evolution and insights gained.
*   **Test-Driven Development (TDD):** Encourage a TDD approach by explicitly mentioning it in the agent's terms of reference.
*   **Configuration and Feature Toggles:** Utilize feature toggles and abstraction to manage complexity and enable incremental development.
*   **Apple Silicon Optimization:**  Consider hardware constraints and optimize for Apple Silicon (if applicable).

## **Project Context Files:**

This repository includes a template set of Project Context files:

*   **`.aiderCode.md` (Terms of Reference):**  Defines the system prompt and instructions for the Aider agent.  This is akin to giving the agent its "role" and expected behavior.
*   **`.aiderContext.md`  (Aider command file):** A command file for aider to add the create/update the project context files into aider 'working memory'
*   **`projectOverview.md` :**  Outlines the project's purpose, goals, user needs, and high-level requirements. 
*   **`systemDesign.md` :** Describes the system's architecture, design patterns, key technical decisions, and high-level technology choices. 
*   **`techEnvironment.md` :**  Focuses on the development environment, dependencies, setup, and troubleshooting. 
*   **`activeDevelopment.md` :** Tracks the current development status, active tasks, recent progress, next steps, and key decisions. 
*   **`testingStrategy.md` (Optional):**  Documents the testing approach, test plans, and test results. *(Optional)*

## **How to Use Precision Prompting with Aider:**

To use Precision Prompting with `aider`, you need to tell Aider to read your terms of reference and load your context files at startup.  Use the `--read` option for `.aiderCode.md` (terms of reference/system prompt) and the `--load` option to specify the list of context files.

## **Example Aider Command:**

```zsh
$ aider <your existing aider options> --read '$HOME/path/to/.aiderCode.md' --load '$HOME/path/to/.aiderContext.md'
```

### Explanation of Command Options:

* aider <your existing aider options>: This is your standard Aider command, including any model selections, project directory specifications, etc.
* --read '$HOME/path/to/.aiderCode.md': This tells Aider to read the .aiderCode.md file and use it as part of the initial prompt. This file contains the terms of reference for the agent.
* --load '$HOME/path/to/.aiderContext.md': This tells Aider to load the files listed in .aiderContext.md into the context.

## Benefits of Precision Prompting:
**Improved Consistency**: The AI agent operates with a clear understanding of project goals, architecture, and technical constraints.

**Enhanced Control**: You have more direct control over the AI agent's behavior through the terms of reference and project context.

**Better Collaboration**: Provides a shared, documented context for you and the AI agent to work together more effectively.

**Scalability and Maintainability**: Structured context makes it easier to manage larger projects and maintain code over time.

**Reduced "Vibe Coding"**: Shifts the focus from ad-hoc prompting to a more planned and intentional approach to AI-assisted development.

**Improved bootstapping**: 'Always up to date' project context ensures mutli-session development can be seemlessly resumed, with no loss of context.  This can even enable multi agent sessions where every agent is aligned on a common goals.

## Use with other tools:
While I built this with use in Aider in mind, I have tried out the approach with Cursor, Cline and Roo.  Each one of these tools was able to seemlessly resume an edit session, even those undertaken by a different tool.  I therefore believe The framework provides a flexible model against which all coding agents can co-exist.

## Thanks to the Aider Team:

This approach is made possible by the excellent aider application. Thank you to the Aider team for creating such a powerful and flexible tool for AI-assisted coding!

## Contribute and Improve:

This is an initial attempt at formalizing "Precision Prompting". Contributions, suggestions, and improvements to the Project Context files, the .aiderCode.md terms of reference, and the overall approach are highly welcome! Please feel free to open issues or pull requests to help refine this methodology.

--------

# RooCode
If you are interested in Agentic Coding, check out my [RooCode custom modes](https://github.com/agileandy/roo-code-modes/)


