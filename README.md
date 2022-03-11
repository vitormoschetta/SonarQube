# Sonarqube 

## Install

```
docker-compose up -d
```

Acessar:

<http://localhost:9001/>


Credenciais primeiro acesso:
user: admin  
pass: admin


Instalar globalmente dotnet-sonarscanner (na máquina que o build no código fonte será executado):
```
dotnet tool install --global dotnet-sonarscanner
```


## Operação

#### Local

É possível buildar um projeto local (seguir orientações na aplicação) e enviar a api do sonar rodando localmente. Basicamente cria-se um projeto no Sonar, que gera um ID. 

Com este ID em mãos rodar os seguintes comandos no diretório da aplicação:
```
dotnet sonarscanner begin /k:<sonar-project-name> /d:sonar.host.url="http://localhost:9001"  /d:sonar.login=<sonar-project-id>
dotnet build
dotnet sonarscanner end /d:sonar.login=<sonar-project-id>
```


