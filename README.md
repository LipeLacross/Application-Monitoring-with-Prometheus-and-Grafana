## 🌐 [English Version of README](README_EN.md)

# Application Monitoring with Prometheus and Grafana

Monitoramento de aplicações e servidores usando Prometheus e Grafana. Esse repositório contém exemplos práticos e configurações para instalação, coleta de métricas, criação de dashboards e configuração de alertas, baseado no curso do instrutor Rodrigo Roma.

## 🔨 Funcionalidades do Projeto

- **Monitoramento em tempo real** de aplicações web e servidores.
- **Coleta automática de métricas** (requisições, usuários logados, tempo de resposta).
- **Visualização de dados** em dashboards intuitivos pelo Grafana.
- **Configuração de alertas** no Prometheus.
- **Integração simples** entre aplicação Node.js, Prometheus e Grafana usando Docker Compose.

### 📸 Exemplo Visual do Projeto

<div style="display: flex; flex-wrap: wrap; gap: 20px; justify-content: space-around;">
  <img src="https://github.com/user-attachments/assets/9de4d1e1-ad0e-4802-8592-58b275dc1a1d" style="width: 60%; border-radius: 8px; box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);">
  <img src="https://github.com/user-attachments/assets/c7f2b411-2b74-444f-9405-b43bff7526ea" style="width: 60%; border-radius: 8px; box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);">
  <img src="https://github.com/user-attachments/assets/9dbccaef-ebab-4379-970c-b7140bd38f02" style="width: 60%; border-radius: 8px; box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);">
</div>

## ✔️ Técnicas e Tecnologias Utilizadas

- **Node.js**: Plataforma de execução JavaScript.
- **Prometheus**: Sistema de monitoramento e alerta.
- **Grafana**: Plataforma de visualização e análise de métricas.
- **Express**: Framework web para Node.js.
- **prom-client**: Biblioteca para expor métricas no formato Prometheus.
- **Docker Compose**: Orquestração de containers para facilitar o ambiente de desenvolvimento e produção[1].

## 📁 Estrutura do Projeto

```
Application-Monitoring-with-Prometheus-and-Grafana/
|-- LICENSE
|-- README.md
|-- docker-compose.yml
|-- index.js
|-- package-lock.json
|-- package.json
|-- prometheus-data/
    |-- prometheus.yml
```

- **LICENSE**: Licença do projeto.
- **README.md**: Documentação principal.
- **docker-compose.yml**: Configuração para rodar Prometheus e Grafana em containers Docker.
- **index.js**: Aplicação Node.js que expõe métricas customizadas.
- **package-lock.json** e **package.json**: Definição das dependências do projeto.
- **prometheus-data/prometheus.yml**: Configuração do Prometheus para coletar métricas da aplicação e do servidor[1].

## 🛠️ Abrir e rodar o projeto

Para iniciar o projeto localmente, siga os passos abaixo:

1. **Certifique-se de que o Node.js está instalado**:
   - O [Node.js](https://nodejs.org/) é necessário para rodar o projeto. Você pode verificar se já o tem instalado com:

     ```bash
     node -v
     ```

   - Se não estiver instalado, baixe e instale a versão recomendada.

2. **Clone o Repositório**:
   - Copie a URL do repositório e execute o comando abaixo no terminal:

     ```bash
     git clone 
     ```

3. **Instale as dependências da aplicação Node.js**:
   - Navegue até a pasta do projeto e execute:

     ```bash
     npm install
     ```

4. **Inicie a aplicação Node.js (opcional, apenas para teste local)**:
   - Execute:

     ```bash
     node index.js
     ```
   - A aplicação estará disponível em `http://localhost:3030` e as métricas em `http://localhost:3030/metrics`.

5. **Suba os serviços com Docker Compose**:
   - Execute o comando abaixo para subir Prometheus e Grafana:

     ```bash
     docker-compose up -d
     ```
   - **Prometheus:** `http://localhost:9090`
   - **Grafana:** `http://localhost:3000`

## 🌐 Deploy

Para fazer o deploy do projeto em um ambiente de produção:

1. **Certifique-se de que Docker e Docker Compose estão instalados** no servidor de destino.
2. **Copie todos os arquivos do projeto** para o servidor.
3. **Suba os serviços** com o comando:

   ```bash
   docker-compose up -d
   ```
4. **Configure domínios e/ou firewalls** conforme necessário para acesso externo.
5. **Proteja o acesso ao Grafana** alterando a senha padrão e restringindo acesso se necessário.

## 📝 Documentação do Código

### **index.js**

Aplicação Node.js que expõe métricas customizadas para o Prometheus:

- **express**: Cria o servidor web.
- **prom-client**: Gera métricas no formato Prometheus.
- **Métricas expostas**:
  - `aula_requests_total`: Contador de requisições, com status code como label.
  - `aula_usuarios_logados_total`: Gauge com o número de usuários logados.
  - `aula_request_duration_seconds`: Histograma do tempo de resposta da API.
- **Endpoints**:
  - `/`: Retorna "Hello World!".
  - `/zera-usuarios-logados`: Zera o contador de usuários logados.
  - `/retorna-usuarios-logados`: Retorna o contador de usuários logados ao valor normal.
  - `/metrics`: Exibe as métricas para o Prometheus coletar[1].

**Observação:** Substitua `` pela URL real do seu repositório ao utilizar este README.  
Para adicionar o README em inglês, crie o arquivo `README_EN.md` com a tradução do conteúdo acima.

