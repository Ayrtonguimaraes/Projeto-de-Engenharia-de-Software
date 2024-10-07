# Documentação da API - NatureLens

---

## 1. Propósito e Funcionalidade

**Descrição Geral:**
- **Propósito:** *Identificar espécies de plantas e animais através de imagens utilizando IA e integração com APIs como Google Gemini Vision Pro e GBIF.*
- **Funcionalidade:** *A API permite que os usuários façam upload de imagens e recebam detalhes sobre a espécie identificada, promovendo conscientização ambiental.*

---

## 2. Especificação Técnica

**Endpoints e Métodos:**
- **URL Base:** *https://api.naturelens.com/v1*
- **Endpoint:** */upload-image*
- **Método:** *POST*

**Parâmetros de Requisição:**
- **Imagem (Obrigatório):** *Arquivo de imagem da planta ou animal.*
- **Token (Obrigatório):** *Chave de autenticação via Google OAuth.*

**Formato de Dados:**
- **Entrada:** *Multipart/form-data*
- **Saída:** *JSON*

---

## 3. Segurança e Autorização

**Autenticação:**
- **Método:** *Google OAuth com Bearer Token.*
- **Cabeçalho de Autenticação:** 
  - *Authorization: Bearer {token}*

---

## 4. Monitoramento e Performance

**Monitoramento:**
- *Ferramentas como Prometheus podem ser utilizadas para monitorar o uso da API (tempo de resposta, requisições, etc.).*

---

## 5. Versionamento

**Versão atual:** *v1*
- *O versionamento é utilizado para garantir compatibilidade com futuras atualizações da API.*

---
