# OpenAI - Demystifying Temperature and TopP

## Intro

Both Temperature and TopP influence the diversity of responses from LLM models. LLMs aren't deterministic systems, meaning return values can differ even if the same prompt is provided to the LLM. This is sometimes an expected behavior but in other cases the results should be more deterministic.

### Temperature

Temperature is a float value with a range between 0 and 1. Where 0 indicates to the model to be more deterministic meaning less variable response should be created. 1 indicates to the model that it can respond with more "creativity" and be less deterministic.

### TopP

TopP can be used to achieve a similar outcome but it works differently. TopP is also a float value between 0 and 1 and it limits the amount of potential responses from a LLM to the request.

Let's assume the LLM has 100 potential tokens to complete the response a TopP value of 0.3 instructs the model to consider just 30 percent of the potential completions. Providing 0 as TopP limits the potential responses to the top completion possibility.

## Samples

Samples how to use Temperature or TopP and both in combination to instruct the model how "creative" responses should be:

[.NET SDK sample](./src/Notebook/DotNetSDK.ipynb)

[Powershell + curl sample](./src/Notebook/PSCurl.ipynb)

## Create Environment

[Azure CLI script](./src/CreateEnv/CreateEnv.azcli) can be used to create Azure resources, deploy an OpenAI model and retrieve the necessary API endpoint, API keys and the deployment name.

## Summary

As seen in the examples Temperature and TopP influence the "creativity" of model responses and can be used in combination.

Sometimes influencing completions from the LLM with one parameter is enough. Therefore as a rule of thumb:

- Influencing responses using Temperature -> Set TopP to 1
- Influencing responses using TopP -> Set Temperature to 1
