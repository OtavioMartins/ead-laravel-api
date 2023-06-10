# Ead Api Laravel 10 - Docker

## Passo a passo
Clone Repositório
```sh
git clone https://github.com/OtavioMartins/ead-laravel-api.git ead-api
```

```sh
cd ead-api/
```
Crie o Arquivo .env

```sh
cp .env.example .env
```


Atualize as variáveis de ambiente do arquivo .env

```sh
APP_NAME=Laravel
APP_URL=http://localhost:8081

DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=ead
DB_USERNAME=root
DB_PASSWORD=root

CACHE_DRIVER=redis
QUEUE_CONNECTION=redis
SESSION_DRIVER=redis

REDIS_HOST=redis
REDIS_PASSWORD=null
REDIS_PORT=6379

URL_FRONTEND=http://localhost:8080

```

Suba os containers do projeto

```sh
docker-compose up -d
```
Acessar o container

```sh
docker-compose exec app bash
```

Instalar as dependências do projeto

```sh
composer install
```
Gerar a key do projeto Laravel
```sh
php artisan key:generate
```

Parar versionamento git
```sh
rm -rf git
```
___
## Caso tenha algum problema com remote no git

Obterá uma lista de identificadores e URLs associados
```sh
git remote -v
```
Para remover URLs associados
```sh
git remote remove origin
```

Migrar tabelas para o bando de dados

```sh
php artisan migrate
```
___
Inserir dados no banco

```sh
php artisan tinker
```
```sh
\App\Models\User::factory(2)->create();
```

```sh
\App\Models\Course::factory()->count(2)->create();
```

```sh
\App\Models\Module::factory()->count(2)->create(['course_id' => 'id do Course']);
```

```sh
\App\Models\Lesson::factory()->count(2)->create(['module_id' => 'id do Module']);
```
___

### Laravel
Acessar o projeto http://localhost:8081

### PHPMYADMIN
Acessar o phpmyadmin http://localhost:8989

Usuario: root

Senha: root

___

## Baixar Vue3 EAD


[Vue3 EAD](https://github.com/OtavioMartins/ead-vue3)

Curso que estudei na plataforma Especializa TI. Já testei com Postman e 
[Vue3 EAD](https://github.com/OtavioMartins/ead-vue3). Código foi digitado, assistindo as aulas, vídeo a vídeo.

___

## Codigo original do curso:


- [Codigo original do curso](https://github.com/especializati/curso-laravel-api-ead)
- [Link do curso Especializa TI](https://academy.especializati.com.br/curso/criando-plataforma-ead-com-laravel)

### Recomendo os cursos. Todos que estudei, são excelente, professor nota 10.

____

## Arquivos diferentes do curso original. Alterados para usar com o [Vue3 EAD](https://github.com/OtavioMartins/ead-vue3)

- app/Http/Resources/ReplySupportResource.php
- app/Http/Resources/SupportResource.php