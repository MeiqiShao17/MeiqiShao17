## Hi there 👋  I'm Miki

<!-- GitHub 状态展示 -->
<img align="center" src="https://github-readme-stats.vercel.app/api?username=MeiqiShao17&show_icons=true&theme=radial" />

<!-- 语言使用统计 -->
<img align="center" src="https://github-readme-stats.vercel.app/api/top-langs/?username=MeiqiShao&layout=compact&theme=radial" />

![description](https://img.shields.io/badge/Language-Python-green)

<!-- 通过style设置徽标样式，通过logo设置icon，通过logoColor设置icon颜色 -->
![Python](https://img.shields.io/badge/Python-3373A7?style=flat-square&logo=python&logoColor=white)

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="/output/github-snake-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="/output/github-snake.svg">
  <img alt="github-snake" src="/output/github-snake.svg">
</picture>

name: generate animation

on:
  # run automatically every 12 hours
  schedule:
    - cron: "0 */12 * * *" 
  
  # allows to manually run the job at any time
  workflow_dispatch:
  
  # run on every push on the master branch
  push:
    branches:
    - master
    
  

jobs:
  generate:
    runs-on: ubuntu-latest
    timeout-minutes: 10
    
    steps:
      # generates a snake game from a github user (<github_user_name>) contributions graph, output a svg animation at <svg_out_path>
      - name: generate github-contribution-grid-snake.svg
        uses: Platane/snk/svg-only@v2
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-snake.svg
            dist/github-snake-dark.svg?palette=github-dark
      # push the content of <build_dir> to a branch
      # the content will be available at https://usercontent.githubfast.com/raw/<github_user>/<repository>/<target_branch>/<file> , or as github page
      - name: push github-contribution-grid-snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

**MeiqiShao17/MeiqiShao17** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
