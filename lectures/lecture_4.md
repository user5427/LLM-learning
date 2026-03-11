# ToC
 
- Tips for programming with LLMs
- Use cases
- Copilot
- Collab

Use LLMs with understanding what is happening.

## Tips:
- Be explicit and precise what you want.
- Dictate what you want in typical way (You express your thoughts faster and more of them)
- Ask LLM to help you to write the description of the task, to generate the question itself.
- Training cut-off, keep that in mind
- Provide context, examples, details, constraints, etc. Treat LLM as a junior programmer. Tell LLM how to scan the codebase for the model to get the context.
- Refactoring.
- Testing the code.

## Edge cases:
- Manual verification
- Customization and adaption
- Contextual understanding

Write for the LLM what to check
Lecturer example:
```python
# distance between two points in 3D space
def distance(point1, point2):
    # Calculate the distance using the formula: sqrt((x2 - x1)^2 + (y2 - y1)^2 + (z2 - z1)^2)
    return ((point2[0] - point1[0]) ** 2 + (point2[1] - point1[1]) ** 2 + (point2[2] - point1[2]) ** 2) ** 0.5
```
Need to check all edge cases, are they not null, etc.

## Generated code security
1. Understand common security issues - bugs in libraries, vulnerabilities, etc.
2. Review and understand the code - static code analysis, OWASP Top 10 issues, etc. SQL injection, XSS, CSRF, etc.
3. Use secure coding practices

You might not tell all that to LLM, but you should be aware of it.

**Tools that help:**
- Static code analysis tools: SonarQube, ESLint, etc.
- Dynamic analysis tools: OWASP ZAP, Burp Suite, etc.
- Dependency scanning tools: Snyk, Dependabot, etc.
- Security guidelines

## how to use LLMs to improve security:
1. Improve context, dont add random code examples
2. Use security-focused prompts
3. Validate outputs
4. Protect your code. (Do not share passwords, as they can get into the training data, etc.)

## Debugging with LLMs
1. Syntax errors
2. Suggesting errors
3. Explaining code

## Tips for debugging:
- Identify the problem
- Isolate the problem
- Understand the code
- Use debugging tools
- Test the fix

**Syntax**, **Logic**, **Runtime** errors.

Prime example was given.

## Code explanation
Understanding, debuging, learning, documentation for the code.

## Function calling
- LLMs can call functions to perform specific tasks, such as fetching data from an API, performing calculations, etc.
For example, you are a weather bot, `get_temperature_for_location(location)`, parameter location, description, usage example. Another `get_rain_probability`, in percents or [0, 1]. For example, location - San Francisco.

- You have to create a thread for the function calling. Runs expire after 10 minutes.

For the streaming case, we create an EventHandler. So based on what funciton is called, we call those functions and then submit the results back to the LLM

# Code conversion

- Transpilers exist, but LLMs can analyze the code and convert it to another language.
Example: Python to Rust.

# Integrating LLMs with CI/CD pipelines
- Code reviews

# Data generation
- Can generate different output formats, such as JSON, CSV, etc. 

- Automated data creation (imaginary)
- Enchanced insights
- Flexibility and scalibility

- Data visualisation (Matplotlib, Seaborn, etc.)

Example: Air Quality Index, data given, generate a graph. Later replace with real data.

# Copilot
<!-- Hey copilot talk about yourself -->
- Code completion
- Code generation
- Code explanation
- Code refactoring
- Code translation
- Code documentation
- Code configuration

**semi-vibecoding** - you write some comment, in comes code suggestions, you can accept, reject, or modify them.

Its context aware, so it can understand the code you are writing and suggest relevant code snippets.

+ Real-time code suggestions
+ Code quality improvement
+ Efficiency boost

It can infer from the function signature, docstring, and the code itself to generate relevant code snippets.

## Unit-test generation
Yeah it can generate those too.
For example: testing addition

**Tips**
- add lots of context
- iterate and review the generated tests

loops to list comprehensions, etc.
recursive functions to iterative ones, etc.

# Google Colab AI assistant
Yeah Gemini exists, does the same as copilot.

Debugingm click the button to explain the error.


# The risk: we will only need to review and do no coding