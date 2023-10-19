## Base de Projetos Com Docker e Rails

DESCRIÇÃO DO PROJETO
Este Repositorio é uma base para criação de projetos futuros usando Docker e Ruby on Rails


### Setup de Desenvolvimento Local

```
    bundle install
```

Estruturar o banco
```
     rails db:migrate
```

Para criar banco
```
      rails db:drop db:create db:migrate
```
Para criar rodar os testes
```
     rspec
```
Subir o servidor 
```
     rails s 
```
Agora a API deve estar disponível em `http://localhost:3000/`.
### Setup de Desenvolvimento Docker

Utilizando Docker e Docker Compose:

```sh
cd api_de_palestras
	ARG_USER_UID=$(id -u) ARG_USER_GID=$(id -g) docker compose config
  ARG_USER_UID=$(id -u) ARG_USER_GID=$(id -g) docker compose build
  docker compose up -d
  docker compose exec app bash
    bundle
    rails db:drop db:create db:migrate
		rspec
    rails s
    # Brower: http://localhost:3000
    # Press: CTRL+C
    exit
  docker compose down
```

### Como Rodar o Projeto

1. Inicie o servidor Rails:

```bash
docker-compose up -d
docker compose exec app bash
  rails s
```

Agora a API deve estar disponível em `http://localhost:3000/`.

### Como Rodar os Testes

1. RSpec para testes de unidade e integração:

    ```bash
    rspec
    ```
