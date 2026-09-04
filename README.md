#  Atividade 05: Implantação IaaS e Containerização com Docker

Este repositório contém a documentação e os arquivos referentes à **Atividade Prática 05** da disciplina de Computação em Nuvem, focada no provisionamento de infraestrutura em nuvem (IaaS) e orquestração de containers web.

---
<br>

##  Resumo da Execução

A atividade foi realizada utilizando o **GitHub Codespaces** (ambiente virtualizado Linux Ubuntu em nuvem IaaS) para contornar limitações locais e garantir paridade de ambiente. Durante a execução, foram aplicados os conceitos de virtualização em nível de SO, mapeamento de portas de rede, persistência de dados via volumes e orquestração declarativa.

---
<br>

##  Etapas Realizadas

1. **Diagnóstico do Ambiente IaaS:**
   * Levantamento de especificações da VM Linux e verificação da versão do Docker Engine no Codespaces.

2. **Deploy de Container Individual (Nginx Padrão):**
   * Execução do container `meu-servidor-web` exposto na porta local `8080` (`8080:80`).

3. **Montagem de Volume e Página Personalizada:**
   * Criação do diretório `./site` contendo um arquivo `index.html` customizado.
   * Inicialização do container `site-customizado` na porta `8081` vinculando o volume persistente ao diretório interno `/usr/share/nginx/html`.

4. **Orquestração com Docker Compose:**
   * Construção do arquivo declarativo `docker-compose.yml` para gerenciamento simplificado do serviço web.
   * Execução da infraestrutura em modo detached (`docker compose up -d`) na porta `8082`.

5. **Acesso Público e Validação:**
   * Redirecionamento e alteração de visibilidade das portas no Codespaces para acesso via URL pública no navegador.

6. **Governança de Recursos:**
   * Parada e remoção de containers ativos via `docker stop` e `docker rm` para prevenir consumo desnecessário de cotas em nuvem.

---
<br>

##  Estrutura do Repositório

```text
.
├── site/
│   └── index.html          # Página HTML personalizada exibida no servidor
├── docker-compose.yml      # Arquivo de orquestração do serviço Nginx
└── README.md               # Documentação do repositório


```
##  Como Executar o Projeto

Para reproduzir este ambiente no GitHub Codespaces ou em qualquer terminal Linux com Docker instalado:


*  Clonar o repositório
```
git clone [https://github.com/SeuUsuario/atividade-5-docker.git](https://github.com/SeuUsuario/atividade-5-docker.git)
cd atividade-5-docker
```
*  Subir o serviço via Docker Compose
```
docker compose up -d
```

*  Verificar os containers em execução
```
docker ps
```

*  Encerrar o serviço
```
docker compose down
```
<br>

## Autor
Aluno: Guilherme Zamboni Menegacio
<br>

## Disciplina: Computação em Nuvem
