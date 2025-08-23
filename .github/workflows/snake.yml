name: GitHub Snake Game

on:
  schedule: # chạy tự động mỗi ngày lúc 0h UTC
    - cron: "0 0 * * *"
  workflow_dispatch: # cho phép chạy thủ công
  push:
    branches:
      - main

permissions:
  contents: write

jobs:
  generate:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Repository
        uses: actions/checkout@v3

      - name: Generate Snake SVG
        uses: Platane/snk@v3
        with:
          github_user_name: phamtrongnhan576
          outputs: |
            dist/github-snake.svg
            dist/github-snake-dark.svg?palette=github-dark

      - name: Push to output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
