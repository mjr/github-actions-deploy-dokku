# Github Actions Deploy Dokku

This action deploys your app to [Dokku](http://dokku.viewdocs.io/dokku~v0.21.4/getting-started/installation/).

## Usage

```yaml
name: Deploy to Dokku

on:
  push:
    branches: [ branch-name ]
  pull_request:
    branches: [ branch-name ]

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v2

      - name: Deploy to Dokku
        uses: mjr/github-actions-deploy-dokku@v2
        with:
          ssh-private-key: ${{ secrets.SSH_PRIVATE_KEY }}
          ssh-port: ${{ secrets.SSH_PORT }}
          dokku-host: ${{ secrets.DOKKU_HOST }}
          app-name: ${{ secrets.DOKKU_APP_NAME }}
```
