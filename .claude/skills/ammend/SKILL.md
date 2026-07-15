---
name: ammend
description: Create the git branch for ammending a document. Also helps a user brainstorm an amendment.
---

i. Preamble. This skill creates a new git branch that adheres to a specific format for tracking amendments to documents in this repository. It accepts optional arguments highlighted in the next section. If no arguments are passed, then the skill only creates the git branch.

ii. Arguments. Optional arguments may be passed in the format --argument-name. The list of current arguments is 
  - --brainstorm - asks the user "what would you like help amending?" Then awaits user input. Read the document and note document content relevant to the user's inquiry. For questions related to the bylaws or charter, invoke section 4. of the /doc-review skill in order to analyze the bylaws and charter. Respond honestly with constructive feedback grounded in the document. Do not search online or make up outlandish suggestions.

**Begin amendment**

1. When invoked, ask the user for two pieces of information
   - the name of the document folder. You present them with a numbered list, each option corresponding to a folder in ./docs.
   - a brief descrption of their amendment. Distil their description down to a key phrase that will reasonably fit in a git branch name.

2. Then take the two pieces of information and create a git branch
  - git branch [response to doc folder]/[distilation of amendment]