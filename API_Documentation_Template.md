# Documentação da API - openAi API

---

## 1. Propósito e Funcionalidade
**Descrição Geral:**
- **Propósito:** Proporcionar uma experiência de planejamento de viagens interativo, onde os usuários podem perguntar sobre destinos, atividades e receber recomendações detalhadas de itinerário, incluindo restaurantes, através da integração com a API da OpenAI.
- **Funcionalidade:** A API permite que os usuários façam perguntas relacionadas a destinos de viagem e atividades, e armazena sugestões geradas por IA para referência futura.

## 2. Especificação Técnica

**Endpoints e Métodos:**
- **URL Base:** (https://api.openai.com/v1).
- **Endpoint:** `/caminho/endpoint`
- **Método Suportado:** `POST`

**Parâmetros de Requisição:**
- **Parâmetros na URL ou Corpo da Requisição:**
 - model (String, Obrigatório): Define o modelo da OpenAI a ser utilizado (ex: "gpt-3.5-turbo").
-messages (Array, Obrigatório): Lista de mensagens que representam a conversa. O primeiro item geralmente define o comportamento da IA, como { role: "system", content: "Você é um assistente de planejamento de viagens." }. Cada interação do usuário é enviada como { role: "user", content: "Pergunta do usuário" }.
  -temperature (Float, Opcional): Ajusta o nível de criatividade das respostas (ex: 0.7).

**Formato de Dados:**
- **Entrada:** JSON.
- **Saída:** JSON.

**Exemplo de Requisição:**
```http
GET /api/endpoint?param1=valor1&param2=valor2 HTTP/1.1
Host: api.exemplo.com
Authorization: Bearer {token}
```

**Exemplo de Resposta:**
```{
  "id": "chatcmpl-abc123",
  "choices": [
    {
      "message": {
        "role": "assistant",
        "content": "Dia 1: Visita à Torre Eiffel... Dia 2: Museu do Louvre..."
      }
    }
  ]
}
```

**Códigos de Resposta e Descrições:**
- **200 OK:** A requisição foi bem-sucedida e a resposta foi retornada corretamente.
- **400 Bad Request:** A requisição contém parâmetros incorretos ou inválidos. Verifique a estrutura e os dados enviados.
- **401 Unauthorized:** A autenticação falhou; geralmente, devido a um token de API inválido ou ausente.
- **404 Not Found:** O endpoint requisitado não existe.
- **429 To many requests:** Excedeu a taxa limite.
- **500 Internal Server Error:** Ocorreu um erro inesperado no servidor.

**Erros Comuns:**
- **Erro 400 - Parâmetro Inválido:** Parâmetros da requisição malformados ou ausentes.
- **Erro 401 - Token Inválido:** A chave de API está incorreta ou ausente.

## 3. Segurança e Autorização

**Autenticação:**
- **Método:** Autenticação por chave de API via Bearer Token
- **Exemplo de Cabeçalho de Autenticação:**
Authorization: Bearer OPENAI_API_KEY

**Autorização:**
- Apenas usuários autenticados com uma chave de API válida podem acessar o endpoint.

**Medidas de Proteção de Dados:**
- **Transmissão Segura:** Uso de HTTPS para todas as requisições.
- **Criptografia:** Chaves API devem ser mantidas em arquivos .env e não devem ser compartilhadas.

## 4. Monitoramento e Performance

**Monitoramento:**
- **Ferramentas Utilizadas:** Ferramentas de monitoramento como Prometheus e Logs podem ser integradas ao backend para monitoramento das requisições e uso da API.
- **Métricas Monitoradas:** Tempo de resposta médio, taxa de erro, número de requisições por minuto, e consumo de recursos.

**Desempenho:**
- **Limites de Taxa (Rate Limits):** A OpenAI impõe limites de requisição, dependendo do plano contratado. Monitorar a taxa de requisição para evitar throttling.
- **Otimização:** Usar técnicas como caching para armazenar respostas frequentes e balanceamento de carga para distribuir requisições.

**Escalabilidade:**
- Utilizar escalabilidade horizontal e balanceamento de carga para garantir que a API suporte aumentos de tráfego sem comprometer a performance.

## 5. Versionamento e Compatibilidade

**Política de Versionamento:**
- A OpenAI utiliza versionamento em seus endpoints. Utilizar o caminho /v1/ para garantir compatibilidade.
- -Mudanças de versão podem afetar a compatibilidade de funções e respostas do modelo.
- **Exemplo:** `/v1/endpoint` ou uso de cabeçalhos específicos para versionamento.

**Compatibilidade:**
- A OpenAI comunica mudanças de versão com antecedência, e a compatibilidade retroativa é mantida sempre que possível. Em casos de quebra de compatibilidade, a documentação é atualizada para facilitar a adaptação.

## 6. Recursos Adicionais

**Links de Referência:**
- [Inclua links para documentos de especificação, tutoriais ou outras fontes úteis que ajudem na compreensão e uso da API.](https://platform.openai.com/docs/api-reference/introduction)


**Nota:** Mantenha esta documentação sempre atualizada com as mudanças na API para evitar problemas de integração e uso indevido.
