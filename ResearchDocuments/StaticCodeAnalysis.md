# Static code analysis
To maintan the quality of our code we use an static code analysis named Sonarcloud. This makes sure before we merge any changes into main and publish it onto docker the quality checks that we have set are met. This is done by four different kind of quality checks that have been explain further down below.

## Sonarcloud quality checks:
- Duplicated lines
 -  duplicate lines refer to identical or nearly identical lines of code that appear multiple times within a codebase.
- Maintainability 
 - The maintainability rating is a metric that provides an assessment of the maintainability of our codebase. It takes these things into account code duplication, code complexity, code smells  readability, maintainability,  and understandability of the code.
- Reliability
 - Reliability refers to the stability of our codebase. It focuses on identifying potential issues and weaknesses that could lead to runtime failures, crashes, or unexpected behavior in our software. 
- Security 
 -Security Hotspots Reviewed allows us to track and manage security hotspots in our codebase. Security hotspots are specific areas of your code that have been flagged as potentially vulnerable or prone to security risks.
