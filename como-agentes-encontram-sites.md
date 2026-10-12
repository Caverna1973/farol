# Como agentes de IA encontram e leem um site

*Pesquisa de 12 de outubro de 2026, para orientar o Farol.*

## 1. Quem lê a web hoje

Há três tipos de robôs de IA:

| Tipo | Exemplos | O que faz |
|---|---|---|
| Robôs de treino e de índice | GPTBot, OAI-SearchBot, Google-Extended | Coletam páginas para treinar modelos ou montar índices |
| Robôs de busca ao vivo | ChatGPT-User, ClaudeBot, PerplexityBot | Abrem a página na hora em que alguém pergunta |
| Agentes de tarefa | Claude Code, agentes em terminal | Abrem o que a tarefa ou o usuário mandar |

Os assistentes também usam os índices dos buscadores: o Gemini usa o do Google e o Copilot usa o do Bing.

## 2. O que funciona de verdade

1. **Ser indexado pelo Google e pelo Bing.** É por aí que a maioria dos assistentes chega. Envie o `sitemap.xml` nos dois. O Bing aceita o IndexNow, que avisa na hora quando algo muda.
2. **Texto no HTML, não só no JavaScript.** A maioria dos robôs não executa JavaScript. O que só aparece via JavaScript fica invisível para eles.
3. **Links de lugares que eles já leem.** GitHub, LinkedIn, artigos, fóruns. O estudo da Ahrefs mostra que robôs de IA abrem arquivos como o `llms.txt` quando um link, um índice ou um usuário aponta para eles.
4. **Dados estruturados (JSON-LD, schema.org).** Dizem às máquinas, sem ambiguidade, o que a página é.

## 3. O que funciona pouco

- **`llms.txt` sozinho.** A Ahrefs analisou 137 mil sites em maio de 2026: 97% dos `llms.txt` não receberam nenhum acesso no mês, e os robôs de busca ao vivo quase não os abriram. Vale manter, porque custa zero, mas não faz milagre.
- **Agent cards (`/.well-known/agent.json`, do protocolo A2A).** Servem para um agente que *oferece um serviço* a outros agentes. O Farol não oferece nenhum, então não usamos.

## 4. Para onde a pesquisa aponta

O artigo *Towards an Agent-First Web* (Bandara et al., 2026) propõe tratar agentes como participantes legítimos da web, com identificação, um arquivo de política `agents.txt` e formatos semânticos com proveniência. É o mesmo espírito do Farol: um sinal público e claro em vez de esconder ou bloquear.

## 5. O que o Farol já fez

- `robots.txt` aberto a todos os robôs, com sitemap.
- `sitemap.xml`, `llms.txt` e `/.well-known/farol.json`.
- Texto do site no próprio HTML (versão de 12/10).
- Dados estruturados JSON-LD.

**Próximos passos:** Google Search Console, Bing Webmaster Tools com IndexNow, e links a partir do GitHub e do LinkedIn.

## Fontes

- Ahrefs — [We Analyzed 137K Sites: 97% of llms.txt Files Never Get Read](https://ahrefs.com/de/blog/llmstxt-study/) (jun. 2026)
- Bandara et al. — [Towards an Agent-First Web: Redesigning the Web for AI Agents](https://arxiv.org/abs/2606.19116) (arXiv, 2026)
- [A Survey of WebAgents](https://arxiv.org/html/2503.23350v4) (arXiv)
- [A Survey of Large Language Model-Based Search Agents](https://preview.aclanthology.org/ingest-acl/2026.acl-long.374/) (ACL 2026)
- P0STMAN — [How AI Agents Discover Websites](https://p0stman.com/how-ai-agents-discover-websites)
