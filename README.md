# Open Prompt

Open prompt is a simple standard to how we can write and manage AI agent prompts while while we update and change them.

> [!NOTE]
> Open prompt is not a best practice model for how to WRITE prompts or something like that. It's just a way to maintain the already written prompt so it can be used, extended, tested and developed easily and better by different people.
> At Dezh we write and maintain all of our prompts in this way.

## Standard V1

This section contains the first version of open prompt standard.

The main structure on your project MUST looks like:

```sh
.
├── prompts
│   └── v1.0.0
│       └── op.json
│       └── prompt.txt
│       └── doc.md
```

The `prompts` directory contains one directory per prompt version.

The prompt itself is kept in `prompt.txt` file. The `op.json` file (open prompt json) contains information and descriptions for the prompt and it's usage. You can find [an example + description of each field on here](./op.jsonc).

The `doc.md` file is a markdown formatted file can contain any human-readable information like red-teaming results, reason for changes, resources and more.

### Tags and Sections

We provide separated information in the prompt using XML-like tags:

- `<name>`: to start.
- `</name>`: to finish.

Here is a list of some standard tags used by us:

1. `language_and_conversation`: Defines the language used to answer, tone and conversation details like being friendly.
2. `tools`: The available MCP tools it can call with details.
3. `general_behavior`: General personality and behavior of agent.
4. `tools_usage`: How/When to use the available tools.
5. `security`: Security notes.

The final format will be like:

```prompt
You are a [ROLE] called [NAME].

<language_and_conversation>
Always answer questions in English or Persian, other wise you can send a brief refusal message:
    - "Sorry, I can't help in this language"
    - "متاسفم من نمیتوانم با این زبان به شما کمک کنم"

Always begin the conversation with a friendly greeting.
</language_and_conversation>

<tools_usage>
Only call a tool if needed and you can't solve the issue without a tool call.
</tools_usage>

// AND THE REST OF PROMPT...
```

>[!NOTE]
> The above prompt is JUST for example to show how the style works with these tags.
