>[!NOTE]
> We may still use it internally, but we no more support updates to this repo and this is archived now.

# Open Prompt

Open prompt is a simple standard to how we can write and manage AI agent prompts while we update and change them.


## Standard V1

This section contains the first version of the open prompt standard.

The main structure of your project MUST look like:

```sh
.
├── prompts
│   └── v1.0.0 | prompt_name
│       └── op.json
│       └── prompt.j2
│       └── doc.md
```

The `prompts` directory contains one directory per prompt version. It can also use git and git tags for version management and name the main directory with project/prompt name. 

The prompt itself is kept in the `prompt.j2` file. We make use of the Jinja to support variables and logics in prompts.

The `op.json` file (open prompt json) contains information and descriptions for the prompt and it's usage. You can find [an example + description of each field on here](./op.jsonc).

The `doc.md` file is a markdown formatted file that can contain any human-readable information like red-teaming results, reason for changes, resources, and more.
