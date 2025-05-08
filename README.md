# AI Pull Request Review Pipeline

## Overview
This repository contains an Azure DevOps pipeline designed to automate the review process for pull requests. 

It leverages Anthropic's 3.7 sonnet model AI to analyse code changes, identify potential issues, and provide actionable feedback directly in the PR. 

## Requirements
- **Continuous Deployment Triggers**: The pipeline is triggered for pull requests targeting the `main` branch. This must be performed manually in azure devops project settings [see here](https://learn.microsoft.com/en-us/azure/devops/pipelines/release/triggers?view=azure-devops#continuous-deployment-triggers).
- **Anthropic API key**: Uses the `claude-3-7-sonnet-20250219` model to analyse the code diff and provide suggestions for improvement. You will need to setup an account with billing and create an API key [see here](https://docs.anthropic.com/en/api/getting-started).
- **Environment Variables**: Properly configured pipeline variables, as outlined in the ``.env``. Ensure the environment variables as outlined in the ``.env`` file are appropriately created and injected into this pipeline. This example retrieves the anthropic API key via our ``Common variables`` group. Substitute your ``Organization`` and ``Project`` settings.
- **Pull Request Permissions** Ensure the signed-in account of the pipelines has permissions to clone, perform ``git`` operations and comment on Azure devops Pull Requests.


## Future Enhancements
- Support for additional programming languages and larger files.
- Improved AI model integration and retry.
- Error handling and logging.