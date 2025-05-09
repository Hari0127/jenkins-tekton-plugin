# Jenkins-Tekton Plugin

![Build](https://img.shields.io/badge/build-passing-brightgreen)
![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg)

> 🔧 Seamlessly trigger and monitor [Tekton](https://tekton.dev) pipelines directly from Jenkins UI. A powerful plugin to bridge the gap between classic CI/CD and modern cloud-native workflows.

---

## Table of Contents

- [Overview](#overview)
- [Goals](#goals)
- [Architecture](#architecture)
- [Features](#features)
- [CI/CD Setup](#cicd-setup)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

This plugin integrates Jenkins with Tekton by providing a graphical interface to trigger Tekton pipelines, view their status, and manage results within Jenkins.

It is intended to simplify DevOps workflows for users looking to adopt Tekton while retaining the familiar Jenkins environment.

---

## Goals

- Enable Jenkins users to:
  - Trigger Tekton pipelines from Jenkins jobs.
  - Monitor Tekton pipeline runs via Jenkins UI.
  - View pipeline run logs and artifacts.
- Ensure a seamless user experience for hybrid CI/CD environments.
- Provide robust documentation and community support.

---

## Architecture

> Architecture Diagram (View with Mermaid-enabled Markdown renderer)

```mermaid
flowchart TD
    A[Jenkins UI] --> B[Plugin Frontend]
    B --> C[REST API Layer]
    C --> D[Tekton Pipelines via Kubernetes API]
    D --> E[Pipeline Execution]
    E --> F[Results to Plugin Backend]
    F --> A
```

⚙️ Features
✅ Jenkins build step to invoke a Tekton PipelineRun

✅ Custom configuration UI for Tekton API server details

✅ Status dashboard for pipeline runs

🔄 Webhook listener for real-time Tekton pipeline updates (WIP)

🔜 Integration with Jenkins Blue Ocean for visual insights

CI/CD Setup
This plugin uses GitHub Actions for Continuous Integration.

Every push and pull request to main runs a Maven build.

Linting and compatibility checks are included using Jenkins test harness.

GitHub Actions Workflow Snippet:

name: CI

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Build with Maven
        run: mvn clean install
Usage
🚧 Installation instructions are under development.

Install the plugin (upload .hpi once it's built).

Go to Jenkins → Tekton Pipelines.

Add your Kubernetes credentials in Jenkins settings.

Choose a pipeline and click Run.

Monitor logs and results in real-time from Jenkins UI.

Contributing
We welcome contributions! ✨

If you’re interested in helping build this plugin:

Fork the repo.

Work on an issue (check the good first issue tag).

Submit a PR and tag a reviewer.

Please follow the Contributor Guidelines (coming soon).

License
This project is licensed under the MIT License.
