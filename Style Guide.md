# API Documentation Notebook Style Guide

## Purpose

This style guide establishes conventions for my API Documentation Notebook, a personal knowledge base for learning and practicing API documentation.

The notebook serves as a reference for concepts, tools, commands, documentation practices, and useful discoveries. Its primary purpose is to help me **understand what I'm learning, retain useful information, and find answers quickly when I need them again**.

Although I may eventually publish the notebook through GitHub Pages, its usefulness as a personal reference takes priority over making it resemble a formal documentation website.

These guidelines are intended to support clarity and consistency, not create unnecessary maintenance work.

## 1. Core principles

Every note should serve a practical purpose: explain something I want to understand, preserve information I might need again, or help me complete a task.

|Principle|Goal|
|---|---|
|**Clarity**|Explain information in a way I can understand without having to revisit the original source.|
|**Accuracy**|Keep technical explanations, commands, and examples correct and reliable.|
|**Completeness**|Capture enough information to make the note useful without documenting everything about the subject.|
|**Consistency**|Use familiar structures and formatting so information is easy to find across notes.|
|**Usability**|Make it easy to locate an answer, understand an example, or follow instructions.|
|**Maintainability**|Keep notes simple enough to update as my knowledge develops.|

**Completeness does not mean exhaustiveness.** A note is complete when it adequately serves its purpose, not when it covers every possible detail.

## 2. Types of notes

Different subjects benefit from different structures. I don't need to force every note into the same template.

|Note type|Purpose|Examples|
|---|---|---|
|**Concept**|Understand what something is, how it works, and why it matters.|HTTP Headers, Authentication, Status Codes|
|**Tool reference**|Remember how to use a tool, including useful commands, options, and examples.|curl, HTTPie, Postman|
|**Documentation practice**|Capture techniques and conventions for writing API documentation.|Documenting Endpoints, Writing Error Responses|

Notes can combine these purposes when doing so makes them more useful.

Instructions, troubleshooting information, and personal discoveries can be included within relevant notes without requiring separate categories.

## 3. Note structure

### Titles

- Use one descriptive H1 heading (`#`) per note.
- Choose titles that clearly identify the subject.
- Use consistent terminology across related notes.
- Keep filenames recognizable and easy to search.

### Introductions

Begin with a short explanation of the subject.

Where relevant, answer:

- What is it?
- What does it do?
- Why is it relevant to API documentation?
- When would I use or encounter it?

The introduction should help me quickly reorient myself when returning to an unfamiliar topic.

### Sections

Use descriptive H2 headings (`##`) to organize the main content and H3 headings (`###`) for subsections.

Organize information in a logical order, typically moving from foundational explanations to examples and more specific details.

Avoid creating headings simply to make a note appear more structured.

### Related notes

Link to relevant concepts and tools when those connections would help me navigate or understand the material.

```
## Related notes

- [[HTTP]]
- [[Authentication]]
- [[curl]]
```

Not every note needs a related-notes section.

## 4. Formatting conventions

Consistent formatting should make information easier to recognize and scan.

### Headings

- Use `#` for the page title.
- Use `##` for primary sections.
- Use `###` for subsections.
- Avoid skipping heading levels.
- Use sentence case for headings.

### Paragraphs

- Keep paragraphs focused on a single idea.
- Prefer straightforward explanations over unnecessarily formal language.
- Define unfamiliar terminology.
- Break up dense explanations when that improves readability.

### Bold text

Use **bold** to highlight important distinctions, key terms, or particularly useful information.

Avoid excessive emphasis.

### Inline code

Use backticks for technical elements such as:

- Commands: `curl`
- Command options: `-H`, `--include`
- HTTP methods: `GET`, `POST`
- Headers: `Content-Type`
- Status codes: `404`
- Filenames: `openapi.yaml`
- Endpoints: `/api/users`
- Literal values: `application/json`

### Code blocks

Use fenced code blocks for complete commands, multi-line examples, JSON, YAML, HTTP messages, and other structured content.

Specify the appropriate language for syntax highlighting.

For example:

```
curl -H "Accept: application/json" \
  https://api.example.com/users
```

Include explanations when the purpose or behavior of an example isn't immediately obvious.

### Tables

Use tables when information benefits from side-by-side comparison or quick lookup.

Good candidates include:

- Command options
- HTTP status codes
- Headers
- Parameters
- Required and optional fields

Keep tables concise. Move lengthy explanations into regular sections when necessary.

### Lists

Use bullet lists for collections of related information.

Use numbered lists when the order of steps matters.

### Callouts

Use Obsidian callouts to highlight information I particularly want to remember.

|Callout|Purpose|
|---|---|
|`[!note]`|Additional context or clarification|
|`[!tip]`|Useful shortcuts or practical advice|
|`[!warning]`|Important limitations or common mistakes|
|`[!example]`|A worked example worth highlighting|

Example:

```
> [!tip]
> curl uses GET by default when no other
> request method is selected.
```

Use callouts selectively so they remain meaningful.

## 5. Technical examples

Examples should help me understand how something works or remind me how to use it.

A useful example should:

1. Demonstrate a specific concept or operation.
2. Use valid syntax.
3. Include enough context to understand it.
4. Avoid unnecessary complexity.
5. Explain important details.

### Commands

When recording a command, include the information I'll need to use it again:

- What the command accomplishes.
- What its important options mean.
- What input it requires.
- What output or behavior to expect, when relevant.

### API requests

Depending on the subject, examples may include:

- HTTP method
- Endpoint URL
- Request headers
- Query parameters
- Request body
- Authentication requirements

### API responses

When useful, include:

- HTTP status code
- Response headers
- Response body
- Explanations of important fields

### Placeholders

Use recognizable placeholders for values that need to be replaced:

- `YOUR_API_KEY`
- `YOUR_TOKEN`
- `https://api.example.com`

Never store actual API credentials or other secrets in the notebook.

### Verification

Test commands and examples when practical.

Distinguish between:

- **Verified examples:** Commands or requests I've successfully tested.
- **Illustrative examples:** Examples created to explain a concept.
- **Unverified information:** Details I haven't yet confirmed.

I don't need to label every example, but I should avoid treating untested behavior as established fact.

## 6. Explaining concepts

Concept notes should help me understand information rather than simply collect definitions.

A useful progression is:

**Definition → Purpose → How it works → Example → Important distinctions**

For example, an HTTP Headers note might explain:

1. What headers are.
2. Why clients and servers use them.
3. How request and response headers differ.
4. What common headers look like.
5. How `Content-Type` differs from `Accept`.

I should explain unfamiliar concepts in enough detail that my future self can understand them without repeating the original lesson.

When a concept already has a dedicated note, link to it rather than duplicating the entire explanation.

## 7. Linking and navigation

Use Obsidian wikilinks to connect related information.

For example:

```
See [[HTTP Headers]] for more information.
```

Organize notes into broad folders:

- `Concepts/`
- `Tools/`
- `Documentation/`

Keep the folder structure relatively shallow.

Create new categories only when the existing organization becomes difficult to navigate.

Use links to connect related subjects rather than creating duplicate notes.

If I publish the notebook using Quartz, Obsidian wikilinks can be preserved. If I want the notes to be directly navigable on GitHub, standard relative Markdown links may be more appropriate.

## 8. Sources and accuracy

The notebook will include information from courses, official documentation, experiments, and personal observations.

To keep it reliable:

- Link to useful original sources.
- Summarize explanations in my own words.
- Record discoveries from hands-on testing.
- Distinguish what I've verified from what I've read or inferred.
- Note relevant version or environment dependencies.
- Revisit information that may become outdated.

Prefer official documentation when verifying technical behavior.

If my testing contradicts a tutorial, investigate the discrepancy rather than assuming either source is automatically correct.

The goal is to develop an accurate understanding, not simply reproduce course material.

## 9. Note review checklist

Use this checklist when reviewing existing notes or deciding whether a new note is ready.

### Content

- Does the note have a clear purpose?
- Can I understand the subject from the introduction?
- Are the technical explanations accurate?
- Have I explained terminology I might forget?
- Does the note contain enough information to be useful later?
- Is anything unnecessary or better suited to another note?

### Structure

- Is the title descriptive?
- Are headings clear and logically organized?
- Does the information follow a sensible progression?
- Are related concepts linked where useful?
- Have I avoided unnecessary duplication?

### Formatting

- Are heading levels consistent?
- Are commands and technical values formatted as code?
- Do code blocks have appropriate syntax highlighting?
- Are tables readable and useful?
- Do lists and callouts improve readability?

### Technical examples

- Is the syntax correct?
- Are important options and parameters explained?
- Is there enough context to understand the example?
- Do I know what behavior or output to expect?
- Have I distinguished verified behavior from illustrative examples when necessary?
- Have I excluded credentials and sensitive information?

### Personal usability

- Can I quickly find the information I'm looking for?
- Does the note answer the questions I would expect it to answer?
- Could I use this information without returning to the original source?
- Will the note still make sense if I revisit it several months from now?

## 10. Definition of done

A note is complete enough when it is **accurate, understandable, organized, and useful to my future self**.

It doesn't need to be exhaustive, perfectly polished, or structured like published product documentation.

Before adding more information, I should ask:

- Will this help me understand or remember the subject?
- Will I realistically need to reference it again?
- Does it belong here or in another note?
- Is the additional detail worth maintaining?

The notebook should evolve alongside my knowledge.

**The goal is to make learning easier, not turn note-taking into another project that requires constant optimization.**