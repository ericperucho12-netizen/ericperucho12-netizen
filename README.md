# ¡Hola! Soy Perucho 👋

![Banner](https://capsule-render.vercel.app/api?type=waving&color=auto&height=200&section=header&text=Bienvenido%20a%20mi%20perfil&fontSize=40&animation=fadeIn)
### 🛠️ Tecnologías y Herramientas

![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=java&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Astro](https://img.shields.io/badge/Astro-BC52EE?style=for-the-badge&logo=astro&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

### 🌐 Conéctate conmigo

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/tu-usuario)
[![TikTok](https://img.shields.io/badge/TikTok-000000?style=for-the-badge&logo=tiktok&logoColor=white)](https://tiktok.com/@tu-usuario)
### 📊 Mis Estadísticas

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=TU_USUARIO_GITHUB&show_icons=true&theme=radial" width="48%" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=TU_USUARIO_GITHUB&layout=compact&theme=radial" width="48%" />
  
</p>
### 🐍 Gráfica de Contribuciones

![Snake animation](https://raw.githubusercontent.com/TU_USUARIO_GITHUB/TU_USUARIO_GITHUB/output/github-contribution-grid-snake.svg)
<details>
<summary><b>🚀 Proyectos Destacados (Haz clic para desplegar)</b></summary>

<br>

- **Proyecto 1:** Breve descripción. [Ver Repositorio](https://github.com/...)
- **Proyecto 2:** Breve descripción. [Ver Repositorio](https://github.com/...)

</details>
name: Generate Snake

on:
  schedule: # Ejecutar cada 12 horas
    - cron: "0 */12 * * *"
  
  workflow_dispatch: # Permitir ejecución manual desde la pestaña Actions
  
  push:
    branches:
    - main

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      
      - uses: Platane/snk@v3
        with:
          # Nombre de usuario de GitHub
          github_user_name: ${{ github.repository_owner }}
          
          # Archivos SVG a generar (uno para tema claro y otro para oscuro)
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
            
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          
      - name: Push to output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
