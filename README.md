# 23people Handbook

This repository is dedicated to storing all company **public consolidated information** in markdown files. This accumulated information is indexed in Vector Store Indexes and utilized by Large Language Models (LLMs) for various tasks related to 23people.

> [!IMPORTANT]
> The **access level** of the files content is `public`, meaning it is accessible to everyone. The content is **not confidential** and can be shared with anyone.

## Use

You can access the handbook in a production environment at [https://manual.23people.io/](https://manual.23people.io).

## Indexing Process

This repository includes a GitHub Action workflow that triggers the indexing of all handbook content into a vector database. When changes are pushed to the main branch, the workflow sends a request to the [23p-handbook-indexer](https://github.com/23people-io/23p-handbook-indexer.git) service, which processes the markdown files and updates the vector index.

## AI Context Resources

The repository includes a special file in the `docs/llm-resources` folder called `handbook-summary.txt`, which contains an up-to-date summary of the entire handbook. This file serves as a context source for AI-powered chatbots and tools.

## Contributing to the Handbook

We follow an open contribution model where team members can propose changes through Pull Requests. This ensures quality and consistency in our documentation.

### Prerequisites

Before you start contributing, make sure you have:

- [Python 3.11.x](https://www.python.org/)
- [Visual Studio Code](https://code.visualstudio.com/) (recommended IDE)
- Git installed on your machine
- A GitHub account with access to the 23people organization

### Development Workflow

1. Clone the repository:

   ```bash
   git clone git@github.com:23people-io/23p-handbook.git
   cd 23p-handbook
   ```

2. Open the project in Visual Studio Code:

   ```bash
   code .
   ```

3. Create a new branch for your changes:

   ```bash
   git checkout -b docs/your-feature-name
   ```

    > [!IMPORTANTE]
    > We create feature branches to:
    > - Keep the main branch stable
    > - Allow for code review before changes are merged
    > - Enable multiple people to work on different features simultaneously
    > - Maintain a clean project history

4. Set up local development environment:

   ```bash
   # Install project dependencies using uv
   uv venv
   uv sync

   # Start the local development server
   uv run start
   ```

   The handbook will be available at `http://localhost:2300` for local preview

5. Make your changes and test them locally by viewing the site in your browser

6. Commit your changes:

   ```bash
   uv run commit
   ```

7. Push your changes to GitHub:

   ```bash
   git push origin docs/your-feature-name
   ```

### Creating a Pull Request

1. Go to the [repository page on GitHub](https://github.com/23people-io/23p-handbook)
2. Click on "Pull requests" and then "New pull request"
3. Select your feature branch as the compare branch
4. Fill in the pull request template with:
   - A clear description of your changes
   - Any relevant context or screenshots
   - Reference to related issues if applicable
5. Submit the pull request
6. Wait for review from the repository maintainers

Your changes will be reviewed by the CODEOWNERS of the repository. They may request changes or provide feedback. Once approved, your changes will be merged into the main branch.

## Technical Information

The project is built using the following technologies:

- **Python 3.11.x**
- [Mkdocs Material](https://squidfunk.github.io/mkdocs-material/)
- Markdown

## Versioning and Commits

This project uses [Conventional Commits](https://www.conventionalcommits.org/) and [Semantic Versioning](https://semver.org/) to maintain a consistent commit history and automated versioning.

### Conventional Commits

When adding changes to the repository, use the following command to commit your changes:

```bash
uv run commit
```

This will launch an interactive prompt that guides you through creating a properly formatted conventional commit message. This structured format helps maintain a clean project history and enables automated version management.

### Semantic Versioning

The project version is not maintained in the `pyproject.toml` file (which has a fixed value of `0.0.0.dev0`), but instead is handled through GitHub releases. When changes are pushed to the `main` branch, a GitHub workflow automatically:

1. Analyzes the commit messages
2. Determines the appropriate version change (major, minor, or patch)
3. Creates a new release with the updated version number

You can view the project's version history and changelog in the [GitHub Releases section](https://github.com/23people-io/23p-handbook/releases).

## Deployment

The deployment is done automatically when you push a new version to the `main` branch. The deployment is done using [Cloudflare Pages](https://pages.cloudflare.com/). The associated Cloudflare Worker is [23people-handbook](https://dash.cloudflare.com/a49f23d59d1f5dc6b2a238d6f4a16ed4/pages/view/23people-handbook). You should be able to see the changes in the production environment after a few minutes under [https://manual.23people.io/](https://manual.23people.io/).

## References

- [Getting started with Mkdocs Material](https://squidfunk.github.io/mkdocs-material/getting-started/)
- [Cloudflare Pages Documentation](https://pages.cloudflare.com/)
- [GitHub Pull Request Documentation](https://docs.github.com/en/pull-requests)
- [Setting up SSH for GitHub](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)

## Contact

If you have any questions or feedback, feel free to reach out to us at `hola@23people.io` or leave an issue [here](https://github.com/23people-io/23p-handbook/issues).

_**We are 23people**, with love **:material-heart:** and passion for technology. Happy Coding! 🚀_
