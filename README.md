# Recipes by my Grandma

Original repo: https://github.com/pathwaycom/pathway

## Introduction

This project is done as part of Gen AI Workshop by Pathway & μLearn. The updates are made in llm-app/examples/pipelines/demo-question-answering.

Add your Gemini API key to the .env file before running this project.

**"Recipes by my Grandma"** is a real-time application that provides easy access to my grandma's latest recipes. This project ingests recipe data stored in PDF format, allowing users to stay up-to-date with her newest creations. Powered by **Pathway**, the application processes any changes made to these PDFs in real-time, adapting instantly. The use of **Docker** ensures that the app is production-ready and easily deployable across environments. At its core, the app features a **Real-time Augmented Generation (RAG)** system, backed by an in-memory scalable vector store that keeps everything fast and up-to-date.

## Table of Contents

1. [What Problem It Solves](#what-problem-it-solves)
2. [Architecture Overview](#architecture-overview)
3. [Getting Started](#getting-started)
4. [Demo](#demo)
5. [Contributing](#contributing)
6. [Contact Information](#contact-information)

## What Problem It Solves

"Recipes by my Grandma" solves the issue of keeping up with ever-evolving family recipes in real-time. Instead of manually tracking recipe changes or sharing new versions individually, this app automates the process by ingesting **PDFs** in the project's data folder. Each time a PDF is added or edited, the app reflects the changes immediately. This feature ensures that users have the latest recipe at their fingertips, whether for personal use or sharing with friends and family.

Additionally, the app can be expanded to connect with **Google Drive** for real-time updates from multiple collaborators or integrated with **300+ data sources** for more sophisticated setups. You can find more details on expanding the functionality in the [Pathway LLM app template](https://github.com/pathwaycom/llm-app?tab=readme-ov-file#llm-app) and [Pathway’s app templates](https://pathway.com/app-templates).

## Architecture Overview

### Pathway

Pathway serves as the primary framework behind this project, enabling **Real-time Augmented Generation** (RAG) capabilities. Pathway allows the application to automatically adapt to new data, offering live updates with minimal latency. It powers the system's ability to handle large-scale data sources while keeping the in-memory vector store optimized for fast retrieval.

### Docker

Docker is used to containerize the entire app, ensuring that it's easy to deploy and maintain across any environment. With Docker, all dependencies are encapsulated, and the app can be effortlessly run with a single command, making the development and production experience seamless.

### Local Data Folder for Data Ingestion

The application reads and processes PDFs stored in the `data/` folder inside the project. As soon as a new PDF is added or an existing one is modified, the system dynamically updates the vector store, ensuring the latest recipes are always available. Additionally, connecting to **Google Drive** or other external sources enables live, collaborative updates to recipes.

## Getting Started

### Prerequisites

- **Docker**: [Install Docker](https://docs.docker.com/get-docker/)
- **Pathway**: You can install Pathway by running:
  ```bash
  pip install pathway-ai
  ```

### Setup Instructions

1. **Clone the repository**:

   ```bash
   git clone https://github.com/your-repo/recipes-by-my-grandma.git
   cd recipes-by-my-grandma
   ```

2. **Build the Docker image**:

   ```bash
   docker build -t grandma-recipes-app .
   ```

3. **Run the Docker container**:

   ```bash
   docker run -d -p 8080:8080 -v $(pwd)/data:/app/data --name grandma-recipes-app grandma-recipes-app
   ```

4. **Adding PDFs**: To add recipes, simply place your recipe PDFs in the `data/` folder. The system will automatically ingest these files and update the content accordingly.

5. **Google Drive Integration** (Optional):
   - For real-time collaboration, set up Google Drive integration by obtaining API credentials and placing them in the `config/drive_credentials.json` file.
   - Specify the Google Drive folder by adding the folder ID in the `.env` file under `GOOGLE_DRIVE_FOLDER_ID`.

## Demo

Here's a placeholder for a video or GIF that demonstrates the app in action:

![Demo Placeholder](demo.gif)

## Contributing

Contributions to improve and expand **Recipes by my Grandma** are welcome! If you're interested in contributing:

1. Fork the repository.
2. Create a new branch.
3. Make your changes.
4. Submit a pull request for review.

Please ensure that your code is well-documented and includes tests when applicable.

## Contact Information

For questions, collaboration, or support, feel free to reach out via:

- LinkedIn: [LinkedIn](https://www.linkedin.com/in/deeprajr/)
- GitHub: [GitHub](https://github.com/DeeprajR)
