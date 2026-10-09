# Versão REST da aplicação de exemplo Spring PetClinic (extensão do spring-framework-petclinic)

[![Status da compilação Java](https://github.com/spring-petclinic/spring-petclinic-rest/actions/workflows/maven-build-master.yml/badge.svg)](https://github.com/spring-petclinic/spring-petclinic-rest/actions/workflows/maven-build-master.yml)
[![Status da compilação da imagem Docker](https://github.com/spring-petclinic/spring-petclinic-rest/actions/workflows/docker-build.yml/badge.svg)](https://github.com/spring-petclinic/spring-petclinic-rest/actions/workflows/docker-build.yml)
[![Status do Quality Gate](https://sonarcloud.io/api/project_badges/measure?project=spring-petclinic_spring-petclinic-rest&metric=alert_status)](https://sonarcloud.io/dashboard?id=spring-petclinic_spring-petclinic-rest)
[![Cobertura](https://sonarcloud.io/api/project_badges/measure?project=spring-petclinic_spring-petclinic-rest&metric=coverage)](https://sonarcloud.io/dashboard?id=spring-petclinic_spring-petclinic-rest)

Esta versão de backend da aplicação Spring Petclinic fornece exclusivamente uma **API REST**. **Não possui interface de usuário (UI)**.

O projeto [spring-petclinic-angular](https://github.com/spring-petclinic/spring-petclinic-angular) é uma aplicação frontend Angular que consome a API REST.

## Conhecendo a aplicação Spring Petclinic por meio de alguns diagramas

[Consulte a apresentação da versão Spring Framework](http://fr.slideshare.net/AntoineRey/spring-framework-petclinic-sample-application)

### Modelo ER da Petclinic

![alt petclinic-ermodel](petclinic-ermodel.png)

## Executando a Petclinic localmente

### Com a linha de comando do Maven

```sh
git clone https://github.com/spring-petclinic/spring-petclinic-rest.git
cd spring-petclinic-rest
./mvnw spring-boot:run
```

### Com Docker

```sh
docker run -p 9966:9966 springcommunity/spring-petclinic-rest
```

Em seguida, você poderá acessar a Petclinic em:

[http://localhost:9966/petclinic/](http://localhost:9966/petclinic/)

Também existe uma rota de verificação de saúde do Actuator:

- [http://localhost:9966/petclinic/actuator/health](http://localhost:9966/petclinic/actuator/health)

## 📖 Documentação da API REST com OpenAPI

Este projeto fornece uma API RESTful para gerenciamento de **proprietários, animais de estimação, veterinários, visitas e especialidades**.

### **Acessando a Swagger UI**

A Swagger UI está disponível em:

[http://localhost:9966/petclinic/swagger-ui.html](http://localhost:9966/petclinic/swagger-ui.html)

A documentação da API (OAS 3.1) está disponível em:

[http://localhost:9966/petclinic/v3/api-docs](http://localhost:9966/petclinic/v3/api-docs)

### 📌 Visão geral dos endpoints da API

| **Método** | **Endpoint** | **Descrição** |
| --- | --- | --- |
| **Owners** |  |  |
| **GET** | `/api/owners` | Recupera todos os proprietários de animais |
| **GET** | `/api/owners/{ownerId}` | Recupera um proprietário de animais pelo ID |
| **POST** | `/api/owners` | Adiciona um novo proprietário de animais |
| **PUT** | `/api/owners/{ownerId}` | Atualiza os dados de um proprietário |
| **DELETE** | `/api/owners/{ownerId}` | Exclui um proprietário |
| **GET** | `/api/owners/{ownerId}/pets/{petId}` | Recupera um animal pelo ID (animal do proprietário) |
| **PUT** | `/api/owners/{ownerId}/pets/{petId}` | Atualiza os dados de um animal (animal do proprietário) |
| **POST** | `/api/owners/{ownerId}/pets` | Adiciona um novo animal a um proprietário |
| **POST** | `/api/owners/{ownerId}/pets/{petId}/visits` | Adiciona uma visita veterinária para um animal |
| **Pets** |  |  |
| **GET** | `/api/pets` | Recupera todos os animais |
| **GET** | `/api/pets/{petId}` | Recupera um animal pelo ID |
| **PUT** | `/api/pets/{petId}` | Atualiza os dados de um animal |
| **DELETE** | `/api/pets/{petId}` | Exclui um animal |
| **Vets** |  |  |
| **GET** | `/api/vets` | Recupera todos os veterinários |
| **GET** | `/api/vets/{vetId}` | Recupera um veterinário pelo ID |
| **POST** | `/api/vets` | Adiciona um novo veterinário |
| **PUT** | `/api/vets/{vetId}` | Atualiza os dados de um veterinário |
| **DELETE** | `/api/vets/{vetId}` | Exclui um veterinário |
| **Pet Types** |  |  |
| **GET** | `/api/pettypes` | Recupera todos os tipos de animais |
| **GET** | `/api/pettypes/{petTypeId}` | Recupera um tipo de animal pelo ID |
| **POST** | `/api/pettypes` | Adiciona um novo tipo de animal |
| **PUT** | `/api/pettypes/{petTypeId}` | Atualiza os dados de um tipo de animal |
| **DELETE** | `/api/pettypes/{petTypeId}` | Exclui um tipo de animal |
| **Specialties** |  |  |
| **GET** | `/api/specialties` | Recupera todas as especialidades veterinárias |
| **GET** | `/api/specialties/{specialtyId}` | Recupera uma especialidade pelo ID |
| **POST** | `/api/specialties` | Adiciona uma nova especialidade |
| **PUT** | `/api/specialties/{specialtyId}` | Atualiza uma especialidade |
| **DELETE** | `/api/specialties/{specialtyId}` | Exclui uma especialidade |
| **Visits** |  |  |
| **GET** | `/api/visits` | Recupera todas as visitas veterinárias |
| **GET** | `/api/visits/{visitId}` | Recupera uma visita pelo ID |
| **POST** | `/api/visits` | Adiciona uma nova visita |
| **PUT** | `/api/visits/{visitId}` | Atualiza uma visita |
| **DELETE** | `/api/visits/{visitId}` | Exclui uma visita |
| **Users** |  |  |
| **POST** | `/api/users` | Cria um novo usuário |

## Captura de tela do cliente Angular

Consulte o repositório em:

https://github.com/spring-petclinic/spring-petclinic-angular

<img width="1427" alt="spring-petclinic-angular2" src="https://cloud.githubusercontent.com/assets/838318/23263243/f4509c4a-f9dd-11e6-951b-69d0ef72d8bd.png">

## Caso encontre um bug ou tenha uma sugestão de melhoria para a Spring Petclinic

O rastreador de issues está disponível em:

https://github.com/spring-petclinic/spring-petclinic-rest/issues

## Configuração do banco de dados

Por padrão, a Petclinic utiliza um banco de dados **H2 em memória**, que é preenchido automaticamente com dados de exemplo durante a inicialização.

### **Bancos de dados suportados**

A Petclinic oferece suporte aos seguintes bancos de dados:

- **H2 (padrão, em memória)**
- **HSQLDB (alternativa, em memória)**
- **MySQL (persistente)**
- **PostgreSQL (persistente)**

### **Alternando o banco de dados**

É possível alterar o banco de dados atualizando a propriedade `spring.profiles.active` no arquivo `application.properties`:

| Banco de dados | Configuração do profile |
| --- | --- |
| **H2** (padrão) | `spring.profiles.active=h2,spring-data-jpa` |
| **HSQLDB** (alternativa em memória) | `spring.profiles.active=hsqldb,spring-data-jpa` |
| **MySQL** (persistente) | `spring.profiles.active=mysql,spring-data-jpa` |
| **PostgreSQL** (persistente) | `spring.profiles.active=postgres,spring-data-jpa` |

Para obter mais detalhes, consulte a [documentação do Spring Boot](https://docs.spring.io/spring-boot/how-to/properties-and-configuration.html#howto.properties-and-configuration.set-active-spring-profiles).

### **Utilizando H2 (padrão)**

- Nenhuma configuração adicional é necessária.
- O esquema do banco de dados e os dados de exemplo são carregados automaticamente a partir de `src/main/resources/db/h2/`.
- É possível acessar o **H2 Console** para inspecionar o banco de dados.

### **Acessando o H2 Console**

1. **Execute a aplicação:**

   ```sh
   mvn spring-boot:run
   ```

2. **Abra o H2 Console no navegador:**

   - **URL**: http://localhost:9966/petclinic/h2-console
   - **JDBC URL**: `jdbc:h2:mem:petclinic`
   - **Usuário**: `sa`
   - **Senha**: _(deixe em branco)_

### **Utilizando HSQLDB**

- O HSQLDB funciona de maneira semelhante ao H2 como um **banco de dados em memória**.
- Nenhuma configuração adicional é necessária — o esquema e os dados de exemplo são carregados automaticamente a partir de `src/main/resources/db/hsqldb/`.
- Para alternar para **HSQLDB**, modifique o arquivo `application.properties`:

```properties
spring.profiles.active=hsqldb,spring-data-jpa
```

### **Utilizando MySQL**

Modifique o arquivo `application.properties`:

```properties
spring.profiles.active=mysql,spring-data-jpa
```

Inicie um banco de dados MySQL utilizando Docker:

```bash
docker run -e MYSQL_USER=petclinic -e MYSQL_PASSWORD=petclinic -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=petclinic -p 3306:3306 mysql:8.4
```

### **Utilizando PostgreSQL**

Modifique o arquivo `application.properties`:

```properties
spring.profiles.active=postgres,spring-data-jpa
```

Inicie um banco de dados PostgreSQL utilizando Docker:

```bash
docker run -e POSTGRES_USER=petclinic -e POSTGRES_PASSWORD=petclinic -e POSTGRES_DB=petclinic -p 5432:5432 postgres:16.3
```

Em vez de executar os contêineres manualmente, também é possível utilizar o `docker-compose.yml`:

```sh
docker-compose --profile mysql up
docker-compose --profile postgres up
```

### **Documentação adicional**

- [HSQLDB](http://hsqldb.org/doc/2.0/guide/index.html)
- [MySQL](https://github.com/spring-projects/spring-petclinic/blob/main/src/main/resources/db/mysql/petclinic_db_setup_mysql.txt)
- [PostgreSQL](https://github.com/spring-projects/spring-petclinic/blob/main/src/main/resources/db/postgres/petclinic_db_setup_postgres.txt)

## Abordagem API First

Esta API é construída seguindo alguns princípios da [abordagem API First](https://swagger.io/resources/articles/adopting-an-api-first-approach/).

A API é especificada por meio da [OpenAPI](https://oai.github.io/Documentation/).

A especificação está neste [arquivo](./src/main/resources/openapi.yml).

Algumas das classes necessárias são geradas durante o processo de build.

Os tipos de arquivos gerados incluem:

- DTOs
- Interfaces de template da API que especificam os métodos a serem sobrescritos nos controllers

Para saber como gerar essas classes, consulte o próximo capítulo.

## Código gerado

Algumas das classes necessárias são geradas durante o processo de build utilizando Maven ou uma IDE, como IntelliJ IDEA ou Eclipse.

Todas essas classes são geradas no diretório:

```text
target/generated-sources
```

Veja abaixo uma lista dos pacotes gerados e das respectivas ferramentas:

| Nome do pacote | Ferramenta |
| --- | --- |
| `org.springframework.samples.petclinic.mapper` | [MapStruct](https://mapstruct.org/) |
| `org.springframework.samples.petclinic.rest.dto` | [OpenAPI Generator Maven Plugin](https://github.com/OpenAPITools/openapi-generator/) |

Para obter ambos, execute o seguinte comando:

```bash
mvn clean install
```

## Configuração de segurança

Na configuração padrão, a Petclinic não possui autenticação e autorização habilitadas.

### Autenticação básica

Para utilizar a funcionalidade de autenticação básica, habilite-a no arquivo `application.properties`:

```properties
petclinic.security.enable=true
```

Isso protegerá todas as APIs e, para acessá-las, será necessária autenticação básica.

Além da autenticação, as APIs também exigem autorização. Isso é realizado por meio das roles que um usuário pode possuir.

As roles existentes são apresentadas abaixo, com as respectivas permissões:

- `OWNER_ADMIN` → `OwnerController`, `PetController`, `PetTypeController` (`getAllPetTypes` e `getPetType`), `VisitController`
- `VET_ADMIN` → `PetTypeController`, `SpecialityController`, `VetController`
- `ADMIN` → `UserController`

Existe um usuário com o nome de usuário `admin` e a senha `admin` que possui acesso a todas as APIs.

Para adicionar um novo usuário, execute uma requisição `POST /api/users` com o seguinte payload:

```json
{
    "username": "secondAdmin",
    "password": "password",
    "enabled": true,
    "roles": [
        { "name": "OWNER_ADMIN" }
    ]
}
```

## Trabalhando com a Petclinic no Eclipse/STS

### Pré-requisitos

Os seguintes itens devem estar instalados no sistema:

- Maven 3 (https://maven.apache.org/install.html)
- Ferramenta de linha de comando `git` (https://help.github.com/articles/set-up-git)
- Eclipse com o plugin m2e (o m2e é instalado por padrão quando é utilizada a distribuição STS (http://www.springsource.org/sts) do Eclipse)

Observação: quando o m2e está disponível, há um ícone `m2` na caixa de diálogo **Help → About**.

Se o m2e não estiver disponível, siga o processo de instalação em:

http://eclipse.org/m2e/download/

- Eclipse com o [plugin MapStruct](https://mapstruct.org/documentation/ide-support/) instalado.

### Etapas

1. Na linha de comando:

   ```sh
   git clone https://github.com/spring-petclinic/spring-petclinic-rest.git
   ```

2. No Eclipse:

   ```text
   File → Import → Maven → Existing Maven project
   ```

## Procurando algo específico?

| Camada | Origem |
| --- | --- |
| Controllers da API REST | [REST folder](src/main/java/org/springframework/samples/petclinic/rest) |
| Service | [ClinicServiceImpl.java](src/main/java/org/springframework/samples/petclinic/service/ClinicServiceImpl.java) |
| JDBC | [jdbc folder](src/main/java/org/springframework/samples/petclinic/repository/jdbc) |
| JPA | [jpa folder](src/main/java/org/springframework/samples/petclinic/repository/jpa) |
| Spring Data JPA | [springdatajpa folder](src/main/java/org/springframework/samples/petclinic/repository/springdatajpa) |
| Testes | [AbstractClinicServiceTests.java](src/test/java/org/springframework/samples/petclinic/service/clinicService/AbstractClinicServiceTests.java) |

## Publicando uma imagem Docker

Esta aplicação utiliza o [Google Jib](https://github.com/GoogleContainerTools/jib) para construir uma imagem Docker otimizada no repositório do [Docker Hub](https://cloud.docker.com/u/springcommunity/repository/docker/springcommunity/spring-petclinic-rest/).

O arquivo [pom.xml](pom.xml) está configurado para publicar a imagem com o nome:

```text
springcommunity/spring-petclinic-rest
```

### Comando para executar

```sh
mvn compile jib:build -X -DjibSerialize=true -Djib.to.auth.username=xxx -Djib.to.auth.password=xxxxx
```

## Testes de desempenho

Para realizar um benchmark da escalabilidade da API REST da PetClinic, está disponível um plano de testes do JMeter.

- Consulte [JMeter Performance Test](src/test/jmeter/README.md) para obter detalhes.
- Execute o teste utilizando:

  ```sh
  jmeter -n -t src/test/jmeter/petclinic-jmeter-crud-benchmark.jmx \
  -Jthreads=100 -Jduration=600 -Jops=2000 -Jramp_time=120 \
  -l results/petclinic-test-results.jtl
  ```

## Testes da API com Postman + Newman

Este projeto contém **testes de não regressão** para a API Petclinic, desenvolvidos com **Postman** e executados por meio do **Newman**, com **relatórios HTML** automatizados para facilitar a análise.

- Consulte [Postman + Newman Test](src/test/postman/README.md) para obter detalhes.
- Os testes podem ser executados de duas formas:

  **I. Concedendo permissão de execução ao arquivo de script:**

  ```sh
  chmod +x postman-tests.sh
  ./postman-tests.sh
  ```

  **II. Sem conceder permissão de execução ao arquivo de script:**

  ```sh
  zsh postman-tests.sh
  ```

> Observação: você também pode utilizar o `bash` já instalado no sistema:

```sh
bash postman-tests.sh
```

## Forks interessantes do Spring Petclinic

A branch `master` do Spring Petclinic no [GitHub da organização spring-projects](https://github.com/spring-projects/spring-petclinic) é a implementação "canônica", atualmente baseada em Spring Boot e Thymeleaf.

Este projeto [spring-petclinic-rest](https://github.com/spring-petclinic/spring-petclinic-rest/) é um dos [vários forks](https://spring-petclinic.github.io/docs/forks.html) hospedados em uma organização específica no GitHub:

[spring-petclinic](https://github.com/spring-petclinic)

Caso você tenha interesse especial em outra stack tecnológica que possa ser utilizada para implementar a Pet Clinic, participe da comunidade.

## Contribuindo

O [issue tracker](https://github.com/spring-petclinic/spring-petclinic-rest/issues) é o canal preferencial para relatar bugs, solicitar funcionalidades e enviar pull requests.

Para pull requests, as preferências do editor estão disponíveis no [editor config](https://github.com/spring-petclinic/spring-petclinic-rest/blob/master/.editorconfig), facilitando o uso em editores de texto comuns.

Saiba mais e baixe plugins em:

<http://editorconfig.org>


## README original em inglês
[README original](readme_original.md)