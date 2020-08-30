# Instalação


### Instale o Docker e o docker compose seguindo as documentações:

[https://docs.docker.com/install/linux/docker-ce/ubuntu/](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

[https://docs.docker.com/compose/install/](https://docs.docker.com/compose/install/)

### Instalação do Docker
Após clonar a pasta do docker execute:

> service docker restart sudo chown $USER /var/run/docker.sock

Acesse:
> cd dockerFileLaravel

e execute:
> sudo cp .env.example .env

Obs: Lembre-se de configurar o arquivo .env de acordo com suas configurações.

para subir os serviços:
> docker-compose up -d

para derrubar: 
> docker-compose down

Depois para utilizar o Docker do Laravel com um repositório específico, acesse o diretório onde fica seus projetos, no meu caso:

> cd html/

> git clone  https://github.com/daniloaldm/api-laravel.git api-laravel

Entre no repositório clonado: 

> cd html/api-laravel

Execute: 

OBS: Configure o arquivo .env de acordo com os seus dados, entretanto no repositório https://github.com/daniloaldm/api-laravel deixei o .env fora do .gitignore e já de acordo com o docker, logo não há necessidade executar esse comando.
> sudo cp .env.example .env

Execute também
> sudo chown -R $USER: $USER /html

Esses 2 últimos comandos devem ser dados dentro do Docker

> docker-compose exec app composer install

> docker-compose exec app php artisan key:generate

Prontinho :heart:

### Executando testes

Acesse o diretório do Docker e execute:

> docker-compose exec app php artisan test

Ou acesse o container executando:

> docker exec -i -t php_service_laravel /bin/bash

e execute:

> php artisan test