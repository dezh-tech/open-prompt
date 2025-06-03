# Open Prompt

Open prompt is a simple standard to how we can write and manage AI agent prompts while while we update and change them.

> [!NOTE]
> Open prompt is not a best practice model for how to WRITE prompts or something like that. It's just a way to maintain the already written prompt so it can be used, extended, tested and developed easily and better by different people.

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
