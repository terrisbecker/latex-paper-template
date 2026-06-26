---
name: doc-review
description: Review and edit documents for clarity, consistency, and accuracy. 
---


i. Preamble. This skill is meant to review Latex documents and suggest edits to improve their clarity, consistency, and accuracy. Specifically, it provides suggestions for the content of a document - it does not suggest formatting changes or edits to Latex syntax. This skill will focus on eliminating loopholes, improving the clarity of the document, and ensuring that it is gramatically and syntactically correct (syntax as in language).

ii. Arguments. The user will privide the path of a file that they want you to review. If they provide multiple paths, review them one at a time, starting with the first path provided. If they provide a path that does not exist, ask them to provide a valid path. If they provide a path that is not a valid document (for example, a code file), ask them to provide a valid path.

iii. References. References are available in the .claude/skills/doc-review/references directory. These include the Elements of Style, an example template of non-profit bylaws, and the LWC bylaws and charter. Refer to these documents as needed to ensure that your suggestions are consistent with the principles outlined in these documents. If at any point you are unsure about a suggestion, refer to these documents for guidance. If you identify any inconsistencies between the document being reviewed and the bylaws or charter, suggest edits to resolve these inconsistencies.

iv. Scope of edits. Read the commit history and version control for the repository. Only propose edits to newly added material and/or old material that may need changed in the context of newly added material.

** Begin document review **

1. Grammar and syntax check. Review the document for any spelling, grammar, or syntax errors. Suggest edits to correct these errors and improve the overall readability of the document. Then commit these edits using git with a clear and concise commit message.

2. Clarity and consistency check. Review the document for any unclear or inconsistent language. For example if a document says it will refer to the Rocky Mountains as "the Rockies", ensure that this terminology is used consistently throughout the document. If numbers are represented as words, ensure this is done consistently. Suggest edits to improve the clarity and consistency of the document. Then commit these edits using git with a clear and concise commit message.

3. Loophole check. Review the document for any potential loopholes or areas of ambiguity that could be exploited or misinterpreted. For example, if a document states that it will go into effect for two years, ensure that it specifies when the two years will begin and end. Suggest edits to eliminate any loopholes or areas of ambiguity. Then commit these edits using git with a clear and concise commit message.

4. Bylaw and Charter check. Review the documents references/lwc-bylaws.md and references/lwc-charter.md. Esnure that the document being reviewed is consistent with the bylaws and charter, and that it does not contradict any of the language or principles outlined in these documents. Ensure that the mission and values of the organization, as outlined in the charter, are reflected in the document. Ensure that any procedures or rules outlined in the bylaws are followed in the document. Suggest edits to ensure consistency with the bylaws and charter. Then commit these edits using git with a clear and concise commit message.

5. Content check. Does the document acheive its intended purpose? Is there anything left unsaid that was promised, in writing, within the document? Do not suggest additional content. Rather, if you identify missing content, suggest edits to the document that will clarify the intended purpose and ensure that all promised content is included. Allow users to deny the suggestions. If they agree to suggestions, then commit these edits using git with a clear and concise commit message. If they deny the suggestions, then do not make any edits to the document.

6. Pull request. After completing the above steps, create a pull request with the suggested edits and a clear and concise description of the changes that were made. If the user has any questions or concerns about the suggested edits, address them in the pull request comments.

7. Conclusion. After completing the above steps, provide a summary of the edits that were made to the document and any remaining issues that may need to be addressed in the future. End the skill here.