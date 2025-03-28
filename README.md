📍 Pontos de Interesse por GPS 🌍
🌟 Descrição
Este projeto foi desenvolvido como parte de um desafio do repositório backend-br e tem como objetivo criar uma API RESTful para localizar Pontos de Interesse (POIs) a partir de coordenadas GPS. A ideia é permitir que os usuários cadastrem POIs, listem todos os POIs cadastrados e encontrem aqueles que estão próximos a uma coordenada específica, dentro de uma distância máxima.

Utilizei Kotlin, Spring Boot e MongoDB para armazenar os dados. A aplicação também conta com Docker para facilitar a configuração do ambiente de desenvolvimento.

🛠️ Tecnologias
Kotlin: Linguagem de programação do back-end.

Spring Boot: Framework utilizado para construir a API RESTful.

MongoDB: Banco de dados NoSQL para armazenar os POIs.

Docker: Usado para configurar o banco de dados em um container.

Postman: Ferramenta utilizada para testar a API.

🔌 Endpoints
Aqui estão os principais endpoints da API:

1. Cadastrar um POI
Método: POST /pois

Request:

json

{
    "name": "Pub",
    "point": {
        "x_coordinate": 12,
        "y_coordinate": 8
    }
}
Response:

json

{
    "name": "Pub",
    "point": {
        "x_coordinate": 12,
        "y_coordinate": 8
    }
}
2. Listar todos os POIs
Método: GET /pois

Response:

json
Copiar
Editar
[
    {
        "name": "Lanchonete",
        "point": {
            "x_coordinate": 27,
            "y_coordinate": 12
        }
    },
    {
        "name": "Posto",
        "point": {
            "x_coordinate": 31,
            "y_coordinate": 18
        }
    },
    {
        "name": "Joalheria",
        "point": {
            "x_coordinate": 15,
            "y_coordinate": 12
        }
    }
]
3. Listar POIs por Proximidade
Método: GET /pois?x_coordinate=20&y_coordinate=10&distance=10

Request:

x_coordinate: Coordenada X do ponto de referência.

y_coordinate: Coordenada Y do ponto de referência.

distance: Distância máxima (em metros) para retornar os POIs.

Response:

json

[
    {
        "name": "Lanchonete",
        "point": {
            "x_coordinate": 27,
            "y_coordinate": 12
        }
    },
    {
        "name": "Joalheria",
        "point": {
            "x_coordinate": 15,
            "y_coordinate": 12
        }
    },
    {
        "name": "Pub",
        "point": {
            "x_coordinate": 12,
            "y_coordinate": 8
        }
    },
    {
        "name": "Supermercado",
        "point": {
            "x_coordinate": 23,
            "y_coordinate": 6
        }
    }
]
🚀 Como Rodar o Projeto
Clone o repositório:

bash

git clone https://github.com/seu-usuario/pontos-de-interesse
Entre no diretório do projeto:

bash

cd pontos-de-interesse
Suba o banco de dados MongoDB utilizando Docker Compose:

bash

docker-compose up
Rode o Spring Boot:


./gradlew bootRun
A API estará disponível em http://localhost:8080.

🧪 Testando a API
Você pode testar a API usando o Postman ou qualquer outra ferramenta de sua preferência. Aqui está um exemplo de requisição para cadastrar um POI:

Exemplo de Requisição
URL: POST http://localhost:8080/pois

Body (JSON):

json

{
    "name": "Pub",
    "point": {
        "x_coordinate": 12,
        "y_coordinate": 8
    }
}
Após cadastrar o POI, você pode listar todos os POIs com o método GET para http://localhost:8080/pois.

📋 Requisitos
Kotlin 1.5 ou superior.

Spring Boot 2.5 ou superior.

MongoDB (pode ser configurado via Docker).

Docker Compose para rodar o banco de dados em container.

💡 Licença
Este projeto está licenciado sob a MIT License.
