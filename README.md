# minha-pagina-web
Este repositório foi criado apenas para fins de estudo.
Este repositório contém uma página web simples e a sua configuração para ser empacotada com Docker e automatizada com GitHub Actions.

## O que foi feito

- Criei o ficheiro `index.html` com um título e o meu nome.
- Criei um `Dockerfile` baseado na imagem  do Nginx, copiando o `index.html` para a pasta padrão do Nginx (`/usr/share/nginx/html`).
- Configurei o GitHub Actions para:
  - Conectar ao DockerHub usando secrets que foram gerados no DockerHub.
  - Fazer o build da imagem Docker: Creie o ficheiro `docker-image.yml`. Adicionei os dois **secrets** gerados anteriormente no repositório GitHub, que são usados na autenticação com o DockerHub.
  - Fazer o push da imagem para o meu repositório no DockerHub: após configurar tudo corretamente, fiz o push do código para o GitHub. Isso ativou o GitHub Actions, que executou automaticamente os passos definidos no ficheiro `docker-image.yml`, incluindo o build da imagem Docker e o push para o meu repositório no DockerHub. No inicio deu um erro devido à falta de permissões, mas após alterar essas permissões no tocken que criei no DockerHub e fazendo o re-run do workflow, correu com sucesso.
 
## Dificuldades encontradas

- Na parte da criação do Token no Docker Hub para usar no GitHub Actions, tive dificuldades em encontrar no GitHub onde poderia colocar esse tockens.
- Quando tentei correr o workflow, tive erro de autenticação no DockerHub por falta de permissões (token com scopes insuficientes). Bastou alterar as permissoes para read/write para corrigir o problema.

No final, o GitHub Actions executou com sucesso o build e o push da imagem para o DockerHub.
