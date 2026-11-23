# LaunchScout

LaunchScout é um radar pessoal para descobrir workshops, virtual summits, free lives e produtos de produtores independentes. O catálogo preserva `source`, `discoveredAt` e `registration` em cada lançamento para manter a proveniência do sinal.

## Executar localmente

```bash
npm install
npm run dev
```

O build de produção é gerado com `npm run build` em `dist/`.

## GitHub Pages

O projeto é uma aplicação estática Vite. Publique o conteúdo de `dist/` usando GitHub Pages ou configure uma Action para executar `npm ci && npm run build` e publicar esse diretório.

## MCP

Abra **Configurações MCP** para criar, editar, pausar ou remover várias fontes. Tokens ficam apenas no `localStorage` deste navegador. O botão **Buscar novidades** tenta consultar o endpoint ativo via `fetch` com CORS e cabeçalho Bearer; se a fonte não responder, a interface continua em modo demo com dados locais.

Para uso real no GitHub Pages, o endpoint MCP precisa aceitar requisições HTTPS do domínio publicado e permitir o header `Authorization` e a origem via CORS. O LaunchScout chama `tools/call` com a ferramenta `search_launches` e normaliza os itens recebidos no catálogo.
