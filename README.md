# Event and city validation and security project
[![NPM](https://img.shields.io/npm/l/react)](https://github.com/luquinhas29/validacao_e_seguranca/edit/main/LICENSE)

## Sobre o projeto
```
Projeto de evento e cidade, relacionado a validação e segurança usando Bean Validation,
Spring Security, Oauth 2, autorização de rotas e perfis,
login e controle de acesso ao banco de dados, validação de testes
```

## Competências
## Modelo de dados de usuários e perfis
- Validação com Bean Validation
- Annotations
- Customizando a resposta HTTP
- Validações personalizadas com acesso a banco
- Login e controle de acesso
- Spring Security
- OAuth 2.0
- Token JWT
- Autorização de rotas por perfil

## Modelo Conceitual do projeto event city
  ![city_event](https://github.com/luquinhas29/validacao_e_seguranca/assets/108932706/74677607-bc37-46bd-bbe7-529a502b25ef)

## Spring Security
## Dependências
```
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-security</artifactId>
</dependency>

<dependency>
	<groupId>org.springframework.security</groupId>
	<artifactId>spring-security-test</artifactId>
	<scope>test</scope>
</dependency>
```

## Spring OAuth2
## Dependências
```
<dependency>
	<groupId>org.springframework.security</groupId>
	<artifactId>spring-security-oauth2-authorization-server</artifactId>
</dependency>

<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-oauth2-resource-server</artifactId>
</dependency>
```

## Valores de configuração
- security.client-id=${CLIENT_ID:myclientid}
- security.client-secret=${CLIENT_SECRET:myclientsecret}
- security.jwt.duration=${JWT_DURATION:86400}
- cors.origins=${CORS_ORIGINS:http://localhost:3000,http://localhost:5173}

## Authorization Server
- Habilitar Authorization server
- Configurar token (codificação, formato, assinatura)
- Configurar autenticação / password encoder
- Registrar aplicação cliente

## Resource Server
- Configurar controle de acesso aos recursos
- Configurar CSRF, CORS
- Configurar token
- Liberar H2 Console no modo teste

## Requisição de login
## Authorization:
```
Tipo: Basic
Username: client-id
Password: client-secret

Body:
Tipo: x-www-form-urlencoded
username: alex@gmail.com
password: 123456
grant_type: password
```
## Controle de acesso por perfil e rota
```
@PreAuthorize("hasRole('ROLE_ADMIN')")

@PreAuthorize("hasAnyRole('ROLE_ADMIN', 'ROLE_OPERATOR')")
```


