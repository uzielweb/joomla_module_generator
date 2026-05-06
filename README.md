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

---

## 🏗️ Estrutura Padrão Joomla 5/6 (Corrigida)

Uma extensão moderna do Joomla deve seguir esta organização para garantir compatibilidade com o instalador e o sistema de Namespaces:

```text
mod_exemplo/
├── language/
│   └── en-GB/
│       ├── mod_exemplo.ini        # Traduções da interface
│       └── mod_exemplo.sys.ini    # Traduções do sistema/instalador
├── media/                         # Ativos públicos (Web Assets)
│   ├── css/
│   ├── js/
│   ├── images/
│   └── joomla.asset.json          # Definição de dependências de ativos
├── services/
│   └── provider.php               # Registro no Service Container (DI)
├── src/                           # Código Fonte (PSR-4)
│   ├── Dispatcher/
│   │   └── Dispatcher.php         # Controlador principal
│   └── Helper/
│       └── ExemploHelper.php      # Lógica de dados/DB
├── tmpl/
│   └── default.php                # Layout (View)
└── mod_exemplo.xml                # Manifesto da Extensão
```

### Por que JSZip?
Toda a inteligência de geração deste projeto reside em **Vanilla JS** (JavaScript puro) dentro dos próprios arquivos HTML. O **JSZip** é utilizado exclusivamente para permitir que o seu navegador consiga agrupar esses diversos arquivos gerados em um único pacote `.zip` baixável, sem a necessidade de processamento no servidor.

---

## 📜 História e Evolução

Este projeto nasceu do **`modulegenerator.php`**, um script PHP básico (Engine Legada) criado para automatizar a estrutura de arquivos do Joomla. Ele ainda está disponível neste repositório como uma ferramenta de linha de comando ou execução direta via servidor local.

Hoje, o projeto evoluiu para um ecossistema completo de ferramentas visuais, oferecendo uma experiência de desenvolvimento muito mais rica e profissional através das interfaces web:

### 🛠️ Como Usar (Escolha sua Versão)

#### Opção A: Web Interface (Recomendado)
Acesse a **[Live Demo](https://uzielweb.github.io/joomla_module_generator/)** e escolha entre as versões **Basic, Intermediate ou Professional** conforme sua necessidade.

#### Opção B: Script PHP (Legado/Servidor Local)
1. Coloque a pasta do projeto no seu servidor local (ex: Laragon/XAMPP).
2. Acesse `localhost/joomla_module_generator/modulegenerator.php`.
3. Preencha o formulário e clique em **Executar** para baixar o `.zip`.

---

## 🏗️ Arquitetura Gerada (Padrão Joomla 5/6)

Independentemente da versão do gerador utilizada, o código resultante segue rigorosamente os padrões modernos do Joomla:

### 1. Services (`/services/provider.php`)
O "coração" da extensão. Utiliza o **Dependency Injection Container** do Joomla para registrar o Dispatcher, o Helper e a própria extensão.

### 2. Dispatcher (`/src/Dispatcher/Dispatcher.php`)
Substitui o antigo arquivo principal do módulo. É o controlador que decide quais dados carregar e qual layout exibir.

### 3. Helper Factory (`/src/Helper/`)
As funções auxiliares (consultas ao banco de dados, processamento de dados) são organizadas em classes Helper que utilizam **Traits** nativas do Joomla.

### 4. Web Asset Manager (`/tmpl/default.php`)
A exibição utiliza o novo gerenciador de ativos do Joomla. CSS e JS são registrados e carregados de forma inteligente.

### 5. Namespaces PSR-4
Todo o código é organizado em Namespaces, garantindo compatibilidade com o autoloader do Joomla.

&copy; 2024-2026 Joomla Extension Generator. Criado para elevar o padrão de desenvolvimento na comunidade Joomla.
