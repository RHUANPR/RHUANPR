<img align="right" height="200" src="https://4maos.com.br/wp-content/uploads/2022/10/aede51ab687ae45145aa59c0c23b62e2.jpg"  />

###

<h1 align="left">oieee👋</h1>

###

<p align="left">oii meu nome é Rhuan e sou programador</p>

###

<h2 align="left">...</h2>

###

<p align="left"></p>

###

<h2 align="left">Codes trabalhados</h2>

###

<div align="left">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" height="40" width="52" alt="html5 logo"  />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" height="40" width="52" alt="css3 logo"  />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" height="40" width="52" alt="javascript logo"  />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/php/php-original.svg" height="40" width="52" alt="php logo"  />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/flutter/flutter-original.svg" height="40" width="52" alt="flutter logo"  />
</div>

###

<div align="left">
  <img src="https://github-readme-stats.vercel.app/api?username=RHUANPR&hide_title=false&hide_rank=false&show_icons=true&include_all_commits=true&count_private=true&disable_animations=false&theme=dracula&locale=pt-br&hide_border=false&order=1" height="166" alt="stats graph"  />
  <img src="https://github-readme-stats.vercel.app/api/top-langs?username=RHUANPR&locale=en&hide_title=false&layout=default &card_width=320&langs_count=2&theme=dracula&hide_border=false&order=2" height="156" alt="languages graph"  />
</div>

###

<div align="center">
  <img height="218" src="https://images.ecycle.com.br/wp-content/uploads/2021/05/20195924/o-que-e-paisagem.jpg"  />
</div>

###

<img src="https://raw.githubusercontent.com/RHUANPR/RHUANPR/output/snake.svg" alt="Snake animation" />

###

<div align="center">
  <img src="https://spotify-recently-played-readme.vercel.app/api?count=5" alt="Spotify recently played"  />
</div>

###

<div align="center">
  <img src="https://github-read-medium-git-main.pahlevikun.vercel.app/latest?limit=4" alt="Layout with last medium posts"  />
</div>

###
# Nome da Actions:  
name: Snake Game

# Controlador do tempo que sera feito a atualização dos arquivos.
on:
  schedule:
      # Será atualizado a cada 5 horas.
    - cron: "0 */5 * * *"

# Permite executar na na lista de Actions (utilizado para testes de build).
  workflow_dispatch:

# Regras
jobs:
  build:
    runs-on: ubuntu-latest
    steps:

    # Checks repo under $GITHUB_WORKSHOP, so your job can access it
      - uses: actions/checkout@v2

    # Repositorio que será utilizado para gerar os arquivos.
      - uses: Platane/snk@master
        id: snake-gif
        with:
          github_user_name: RHUANPR #Seu usuario
          gif_out_path: dist/github-contribution-grid-snake.gif
          svg_out_path: dist/github-contribution-grid-snake.svg

      - run: git status

      # Para as atualizações.
      - name: Push changes
        uses: ad-m/github-push-action@master
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          branch: master
          force: true

      - uses: crazy-max/ghaction-github-pages@v2.1.3
        with:
          # the output branch we mentioned above
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
