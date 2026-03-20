# Java Spring Boot SOA - Microserviços com RabbitMQ

Este projeto demonstra a implementação de uma **Arquitetura Orientada a Serviços (SOA)** utilizando **Spring Boot** e mensageria assíncrona com **RabbitMQ**. O sistema é composto por dois microserviços que se comunicam para automatizar o envio de e-mails de boas-vindas após o cadastro de um novo usuário.

## Arquitetura do Projeto

O projeto segue o padrão de comunicação assíncrona para garantir o desacoplamento entre os serviços:

1.  **User Service**: Gerencia o cadastro de usuários no banco de dados (MySQL) e publica um evento na fila do RabbitMQ.
2.  **RabbitMQ (Broker)**: Recebe a mensagem do User Service e a armazena de forma segura até que seja consumida.
3.  **Email Service**: Escuta a fila, consome a mensagem e realiza o envio real do e-mail através do servidor SMTP do Google.

---

## Tecnologias Utilizadas

* **Linguagem:** Java 17
* **Framework:** Spring Boot 3.x
* **Mensageria:** RabbitMQ (via CloudAMQP)
* **Banco de Dados:** MySQL (JPA/Hibernate)
* **Segurança/Envio:** JavaMailSender (SMTP Gmail)
* **Ferramentas:** Maven, ThunderClient/Postman

---
