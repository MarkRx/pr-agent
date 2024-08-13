# Installation

## Self-hosted PR-Agent
If you choose to host you own PR-Agent, you first need to acquire two tokens:

1. An OpenAI key from [here](https://platform.openai.com/api-keys), with access to GPT-4 (or a key for [other models](../usage-guide/additional_configurations.md/#changing-a-model), if you prefer).
2. A GitHub\GitLab\BitBucket personal access token (classic), with the repo scope. [GitHub from [here](https://github.com/settings/tokens)]

There are several ways to use self-hosted PR-Agent:

- [Locally](./locally.md)
- [GitHub](./github.md)
- [GitLab](./gitlab.md)
- [BitBucket](./bitbucket.md)
- [Azure DevOps](./azure.md)

## PR-Agent Pro 💎
PR-Agent Pro, an app hosted by CodiumAI for GitHub\GitLab\BitBucket, is also available. 
<br>
With PR-Agent Pro, installation is as simple as signing up and adding the PR-Agent app to your relevant repo. 
See [here](./pr_agent_pro.md) for more details.

# Advanced Configuration

## Integrating with Logging Observability Platforms

Various logging observability tools can be used out-of-the box when using the default LiteLLM AI Handler. Simply configure the LiteLLM callback settings in `configuration.toml` and set environment variables according to the LiteLLM [documentation](https://docs.litellm.ai/docs/).

For example, to use [LangSmith](https://www.langchain.com/langsmith) you can add the following to your `configuration.toml` file:
```
[litellm]
...
success_callback = ["langsmith"]
failure_callback = ["langsmith"]
service_callback = ["langsmith"]
```

Then set the following environment variables:

```
LANGSMITH_API_KEY=<api_key>
LANGSMITH_PROJECT=<project>
LANGSMITH_BASE_URL=<url>
```