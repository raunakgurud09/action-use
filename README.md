# Action use


Automate your blogging workflow! This GitHub Action enables you to effortlessly publish your Markdown file to Hashnode with a single push. Say goodbye to manual steps and hello to streamlined publishing.

## Usage

To integrate this action into your workflow, follow these steps:

1. **Create a Workflow File:**
   - In your repository, create a workflow file (e.g., `.github/workflows/publish.yml`).

2. **Define the Workflow:**
   - Add the following steps to your workflow file:

   ```yaml
   name: Publish to Hashnode

   on:
     push:
       branches:
         - main

   jobs:
     publish:
       runs-on: ubuntu-latest
       steps:
         - name: Checkout Repository
           uses: actions/checkout@v2

         - name: Publish to Hashnode
           uses: raunakgurud09/hashnode-publish@v2
           with:
             hashnode_key: ${{ secrets.HASHNODE_KEY }}
             file: "path/to/your/markdown/file.md"
             host: "yourBlogUrl.hashnode.dev"
   ```

3. **Configure Secrets:**
   - In your repository settings, add the `HASHNODE_KEY` secret. Get your Hashnode key from [Hashnode Dashboard](https://hashnode.com/settings/developer).

4. **Commit and Push:**
   - Commit your workflow file changes and push to the specified branch (e.g., `main`).

## Inputs

- `hashnode_key` (required): Your Hashnode API key. Add it as a secret in your repository.
- `file_path` (required): Path to the Markdown file you want to publish. Should be relative to the repository root.
- `host` (optional): The hostUrl of the blog you want to publish on. Recommended to give

## Contribution

Contributions are welcome! Feel free to open issues or submit pull requests to enhance this action.

Happy blogging! 🚀✨