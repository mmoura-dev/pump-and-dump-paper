## Trabalhando com LaTeX
Para conseguir trabalhar com LaTeX no vscode é necessário instalar a extensão [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) e configurar um compilador.

### Configurando LaTeX localmente usando Docker
1. Instale o Docker e configure seu usuário como membro do grupo `docker` para que não seja necessário utilizar sudo.
2. Obtenha a imagem do LaTeX - obs: ela possui mais de 2GB de tamanho.
```bash
docker pull tianon/latex
```
3. Configure a extensão `LaTeX Workshop` para usar a imagem Docker.
    - Abra a `Command Pallet`(Ctrl + Shift + p) do vscode e busque por `Open Settings (JSON)`.
    - Adicione as seguintes configurações ao final do arquivo:
    ```json
    "latex-workshop.view.pdf.viewer": "tab",
    "latex-workshop.docker.enabled": true,
    "latex-workshop.latex.outDir": "./out",
    "latex-workshop.synctex.afterBuild.enabled": true,
    "latex-workshop.docker.image.latex": "tianon/latex",
    ```