# :package: Continuous Integration (CI) and Continuous Deployment (CD) for the NARPS open pipelines project

:mega: This file descripes how CI/CD works for the project.

## CI on GitHub

GitHub allows to launch CI workflows using [Actions](https://docs.github.com/en/actions).

See GitHub's documentation on [worflow syntax](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions) to write your own workflows.

These worflows are YAML files, located in the `.github/workflows/` directory. For now, this directory contains:

* [code_quality.yml](/.github/workflows/code_quality.yml)
	* **What does it do ?** It performs a static analysis of the python code (see the [testing](/docs/testing.md) topic of the documentation for more information).
	* **When is it launched ?** For every push on the repository, if there are changes on `.py` files. You can always [prevent GitHub from running a workflow](https://docs.github.com/en/actions/managing-workflow-runs/skipping-workflow-runs)
	* **Where does it run ?** On GitHub servers.
	* **How can I see the results ?** Outputs (logs of pylint) are stored as [downloadable artifacts](https://docs.github.com/en/actions/managing-workflow-runs/downloading-workflow-artifacts) during 15 days after the push.