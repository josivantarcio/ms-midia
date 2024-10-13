# Sistema de Apresentação com Microsserviços

Este projeto é um exemplo de sistema baseado em microsserviços, desenvolvido em **Java 11** utilizando **Spring Boot 2.3.4**. O objetivo é apresentar a arquitetura e funcionalidades de um sistema modularizado que pode ser escalado e mantido de forma eficiente.

## Tecnologias Utilizadas

- **Java 11**: Linguagem de programação principal.
- **Spring Boot 2.3.4**: Framework para desenvolvimento dos microsserviços.
- **Maven**: Gerenciamento de dependências e build do projeto.
- **Docker**: Para containerização dos microsserviços.
- **Spring Cloud**: Para implementação de padrões de microsserviços como discovery, gateway, e configuração distribuída.
- **PostgreSQL** (ou outro banco de dados): Para persistência de dados.
- **Eureka**: Serviço de descoberta de microsserviços.
- **Feign Client**: Para comunicação entre microsserviços.

## Estrutura do Projeto

Este projeto segue uma arquitetura de microsserviços. Cada serviço está contido em seu próprio módulo e pode ser iniciado e desenvolvido de forma independente.

- **Service Discovery**: Implementado com **Eureka** para registro e descoberta de serviços.
- **Gateway**: Um gateway para rotear as requisições para os serviços apropriados.
- **Serviços Individuais**: Microsserviços que realizam funções específicas. Por exemplo:
  - **User Service**: Gerenciamento de usuários.
  - **Order Service**: Processamento de pedidos.
  - **Product Service**: Gerenciamento de produtos.

## Como Executar o Projeto

1. **Clonar o repositório**:
   
   ```bash
   git clone https://github.com/seu-usuario/nome-do-repositorio.git
   cd nome-do-repositorio
   ```

2. **Construir o projeto com Maven**:
   
   Execute o seguinte comando para compilar e baixar as dependências:

   ```bash
   mvn clean install
   ```

3. **Iniciar os microsserviços**:
   
   Cada microsserviço pode ser iniciado separadamente. Navegue até o diretório de cada serviço e execute o seguinte comando:

   ```bash
   mvn spring-boot:run
   ```

4. **Utilizando Docker (Opcional)**:
   
   Para facilitar a execução, você pode usar Docker para containerizar e executar os serviços:

   - **Construir a imagem Docker**:
     
     ```bash
     docker build -t nome-da-imagem .
     ```

   - **Iniciar o contêiner**:

     ```bash
     docker run -p 8080:8080 nome-da-imagem
     ```

## Configurações

Certifique-se de ajustar as configurações de conexão com o banco de dados e outros serviços no arquivo `application.yml` ou `application.properties` em cada microsserviço. Exemplo de configuração para PostgreSQL:

```yaml
spring:
  datasource:
    url: jdbc:postgresql://localhost:5432/seu_banco_de_dados
    username: seu_usuario
    password: sua_senha
```

## Contribuição

Sinta-se à vontade para contribuir com melhorias ou novos recursos através de pull requests.

## Licença

Este projeto está sob a licença [MIT](LICENSE).
