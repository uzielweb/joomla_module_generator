# Joomla Extension Generator Professional
**The Ultimate Scaffolding Ecosystem for Modern Joomla Development (v4, v5, and v6)**

[![Live Demo](https://img.shields.io/badge/Live-Demo-brightgreen?style=for-the-badge&logo=joomla)](https://uzielweb.github.io/joomla_module_generator/)

## 🌟 Visão Geral do Projeto
O **Joomla Extension Generator** é um ecossistema completo de ferramentas de scaffolding projetado para eliminar o trabalho repetitivo na criação de extensões para Joomla. Ele não apenas gera arquivos, mas implementa uma **arquitetura de nível corporativo** baseada nos padrões mais recentes do núcleo do Joomla.

Se você é um desenvolvedor que busca produtividade, este projeto oferece três níveis de automação para atender desde módulos simples até componentes e plugins complexos com lógica de banco de dados e APIs.

---

## ⚡ Níveis de Geração (Tiers)

Este repositório abriga três versões distintas do gerador, cada uma focada em um nível de complexidade:

### 1. 🟢 Basic Generator (`index.html`)
Ideal para iniciantes ou módulos rápidos que não requerem configurações complexas.
- Gera a estrutura básica (Dispatcher, Helper, Provider).
- Suporte a metadados essenciais e namespaces.
- Download instantâneo de pacotes .ZIP.

### 2. 🚀 Intermediate Generator (`joomla-module-generator-intermediate.html`)
Focado em módulos funcionais com interface de usuário.
- **+12 Templates Prontos**: Hero, Carrossel, FAQ, Galeria, Tabela de Preços, etc.
- **Arquitetura MVC**: Separação clara entre dados e exibição.
- **Web Asset Manager**: Enfileiramento automático de JS/CSS.
- **Suporte Multilíngue**: Geração de arquivos `.ini` para múltiplos idiomas.

### 3. ⚡ Professional Generator (`joomla-module-generator-professional.html`)
A ferramenta definitiva para desenvolvedores sêniores e agências.
- **Fields Architect**: Interface visual para criar formulários com os **~75 tipos de campos nativos do Joomla**.
- **Subforms Dinâmicos**: Suporte a campos repetíveis (repeatable-grid) com campos filhos.
- **Integração SQL**: Lógica de banco de dados pré-configurada.
- **AJAX & REST**: Endpoints preparados para interações assíncronas.
- **Exportação JSON**: Salve suas configurações para editar ou compartilhar futuramente.

---

## 🚀 Principais Recursos Técnicos
- **Compatibilidade Total**: Suporte garantido para Joomla 4.4, Joomla 5.x e o futuro Joomla 6.
- **Padrões PSR**: Código gerado com Namespaces e Autoloading (PSR-4).
- **Service Providers**: Implementação nativa do padrão de Injeção de Dependência.
- **Modern Dispatchers**: Controle centralizado de requisições conforme o novo padrão do Core.
- **Zero Dependências**: Funciona inteiramente no navegador (Client-side) usando JSZip.

### 🛠️ How to Use
1. Clone this repository or download the `modulegenerator.php` file.
2. Access the generator via your local server (e.g., `localhost/joomla_module_generator/modulegenerator.php`).
3. Fill out the form with your module details (Name, Author, etc.).
4. Click **Execute** and download your ready-to-install `.zip` package.

![Joomla Module Generator Interface](https://github.com/user-attachments/assets/edfa387b-df9d-4e36-99dd-734656c8c5f4)

![image](https://github.com/user-attachments/assets/5e7d755a-21d1-4f96-8adc-9892765e9450)

## This is the default Joomla 5 Module structure
```
mod_hello/
│
├── language/               # Language folder and files
│   └── en-GB/  
│       ├── mod_hello.ini          # Text displayed by the module
│       └── mod_hello.sys.ini      # Metadata (name and description)
│
├── media/                  # Static resources
│   ├── css/style.css                # Module CSS Styles
│   ├── images/             # Images used by the module
│   └── js/script.js                 # Scripts JavaScript
│
├── services/               # Dependency injection services
## 📜 História e Evolução

Este projeto nasceu do **`modulegenerator.php`**, um script PHP básico (Engine Legada) criado para automatizar a estrutura de arquivos do Joomla. Ele ainda está disponível neste repositório como uma ferramenta de linha de comando ou execução direta via servidor local.

Hoje, o projeto evoluiu para um ecossistema completo de ferramentas visuais, oferecendo uma experiência de desenvolvimento muito mais rica e profissional através das interfaces web:

---

## 🏗️ Arquitetura Gerada (Padrão Joomla 5/6)

Independentemente da versão do gerador utilizada, o código resultante segue rigorosamente os padrões modernos do Joomla:

### 1. Services (`/services/provider.php`)
O "coração" da extensão. Utiliza o **Dependency Injection Container** do Joomla para registrar o Dispatcher, o Helper e a própria extensão. Isso torna o módulo modular e fácil de testar.

### 2. Dispatcher (`/src/Dispatcher/Dispatcher.php`)
Substitui o antigo arquivo principal do módulo. É o controlador que decide quais dados carregar e qual layout exibir. Ele gerencia o fluxo de execução de forma limpa.

### 3. Helper Factory (`/src/Helper/`)
As funções auxiliares (consultas ao banco de dados, processamento de dados) são organizadas em classes Helper que utilizam **Traits** nativas do Joomla para acesso seguro ao banco de dados.

### 4. Web Asset Manager (`/tmpl/default.php`)
A exibição utiliza o novo gerenciador de ativos do Joomla. CSS e JS não são mais injetados manualmente, mas registrados e carregados de forma inteligente pelo núcleo, evitando conflitos.

### 5. Namespaces PSR-4
Todo o código é organizado em Namespaces (ex: `Joomla\Module\SeuModulo`), eliminando a necessidade de dezenas de `require_once` e garantindo compatibilidade com o autoloader do Joomla.

---

## 🛠️ Como Usar (Escolha sua Versão)

### Opção A: Web Interface (Recomendado)
Acesse a **[Live Demo](https://uzielweb.github.io/joomla_module_generator/)** e escolha entre as versões **Basic, Intermediate ou Professional** conforme sua necessidade.

### Opção B: Script PHP (Legado/Servidor Local)
1. Coloque a pasta do projeto no seu servidor local (ex: Laragon/XAMPP).
2. Acesse `localhost/joomla_module_generator/modulegenerator.php`.
3. Preencha o formulário e clique em **Executar** para baixar o `.zip`.

---

## 📁 Estrutura do Pacote Gerado
```text
mod_exemplo/
├── language/ en-GB/       # Traduções (.ini e .sys.ini)
├── media/                 # CSS, JS e Imagens (Web Assets)
├── services/              # Injeção de Dependência (provider.php)
├── src/                   # Lógica (Dispatcher e Helpers)
├── tmpl/                  # Layouts (default.php)
└── mod_exemplo.xml        # Manifesto (Manifest)
```

&copy; 2024-2026 Joomla Extension Generator. Criado para elevar o padrão de desenvolvimento na comunidade Joomla.
