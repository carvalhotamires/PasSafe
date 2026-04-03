# 🔐 PasSafe - E-mail Centric Vault & Chrome Extension

<p align="center">
  <img src="https://img.shields.io/badge/Java-17-orange?style=for-the-badge&logo=java" alt="Java 17">
  <img src="https://img.shields.io/badge/Spring_Boot-3.x-green?style=for-the-badge&logo=springboot" alt="Spring Boot">
  <img src="https://img.shields.io/badge/PostgreSQL-latest-blue?style=for-the-badge&logo=postgresql" alt="PostgreSQL">
  <img src="https://img.shields.io/badge/Chrome_Extension-Manifest_V3-blue?style=for-the-badge&logo=googlechrome" alt="Chrome Extension">
</p>

> **🛡️ Descrição:** Motor de cibersegurança projetado para atuar como um cofre digital inteligente. O **PasSafe** centraliza e protege credenciais e chaves TOTP (2FA) vinculadas estritamente à identidade (e-mail) do usuário, servindo como o back-end de uma extensão nativa para Google Chrome.

---

## 🎯 O Conceito: Identidade como Âncora

Diferente de gerenciadores genéricos, o **PasSafe** organiza a segurança em torno do e-mail do usuário. Cada segredo armazenado é vinculado a uma identidade única, garantindo que o fluxo de recuperação e acesso seja sempre autenticado e auditado.

### ✨ Funcionalidades Principais

* **Cofre Baseado em Identidade:** Organização automática de senhas e segredos vinculados ao e-mail do proprietário.
* **Engine de Extensão:** API preparada para integração via Manifest V3, permitindo preenchimento automático (Auto-fill) no navegador.
* **Criptografia de Ponta:** Armazenamento em banco de dados PostgreSQL utilizando cifra AES-256 para garantir que apenas o dono do e-mail acesse os dados.
* **Gestor TOTP Integrado:** Geração de códigos temporários de 6 dígitos (A2F) sincronizados diretamente na extensão.
* **Logs de Auditoria:** Registro de todas as tentativas de acesso e alterações para garantir a integridade do cofre.

---

## 🛠️ Stack Tecnológica

### **Back-end (A API do Cofre)**
* **Linguagem:** Java 17
* **Framework:** Spring Boot 3.x
* **Segurança:** Spring Security + Autenticação via JWT (Stateless).
* **Banco de Dados:** PostgreSQL (Persistência Relacional).
* **Mapeamento:** Hibernate / Spring Data JPA.

### **Front-end (A Interface no Chrome)**
* **Padrão:** Chrome Extension Manifest V3.
* **Linguagens:** HTML5, CSS3 e JavaScript.

---

## 📂 Arquitetura do Sistema

O projeto segue os padrões de mercado para desenvolvimento de Back-end Avançado:

* **`com.br.passafe.entities`**: Mapeamento das tabelas de Usuários (ID via E-mail) e Segredos.
* **`com.br.passafe.dtos`**: Camada de proteção para tráfego de dados sensíveis entre Extensão e API.
* **`com.br.passafe.services`**: Implementação das regras de negócio e algoritmos de criptografia.
* **`com.br.passafe.config`**: Configuração de CORS para permitir a comunicação segura com a extensão do navegador.

