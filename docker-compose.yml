version: '3.8'

services:
  frontendg:
    restart: unless-stopped
    image: gvilliger/frontend223
    container_name: frontendg
    depends_on:
      - backend
    ports:
      - 8907:80
  backendg:
    restart: unless-stopped
    image: gvilliger/backend223
    container_name: backendg
    ports:
      - 8080:8080
    depends_on:
      - db

    environment:
      environment:
      SPRING_DATASOURCE_URL: jdbc:postgresql://dbg:5432/postgres
      SPRING_DATASOURCE_USERNAME: postgres
      SPRING_DATASOURCE_PASSWORD: postgres
      SPRING_JPA_DATABASE-PLATFORM: org.hibernate.dialect.PostgreSQLDialect
      SPRING_JPA_DEFER-DATASOURCE-INITIALIZATION: true
      SPRING_JPA_HIBERNATE_DDL-AUTO: create
      LOGGING_LEVEL_ROOT: info
      SPRING_SQL_INIT_MODE: always
      JWT_SECRET: AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA
      JWT_ISSUER: uk223
      JWT_EXPIRATIONMILLIS: 100000000
    
  dbg:
    restart: unless-stopped
    image: 'postgres'
    container_name: dbg
    ports:
      - '5432:5432'
    environment:
      POSTGRES_PASSWORD: 'postgres'
      POSTGRES_USER: 'postgres'
      POSTGRES_DB: 'postgres'
