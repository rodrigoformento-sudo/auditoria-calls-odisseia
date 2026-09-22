# Auditor de Calls

Plataforma de auditoria de calls comerciais. Organiza por cliente, permite frameworks de critérios totalmente customizáveis, dá veredito item a item com evidência obrigatória, e gera um ranking de aderência entre todas as calls.

Roda inteira no navegador, sem servidor. Usa sua própria chave da API Anthropic e guarda os dados em localStorage (por navegador).

## Como publicar no GitHub Pages

1. Crie um repositório novo no GitHub.
2. Suba `index.html` e `README.md` pra raiz do repositório.
3. Adicione também um arquivo vazio chamado `.nojekyll` na raiz (evita que o GitHub tente processar o site com Jekyll e sirva a página errada).
4. Em **Settings > Pages**, escolha **Deploy from a branch**, branch `main`, pasta `/ (root)`. Salve.
5. Em 1 a 2 minutos o link fica disponível em `https://seu-usuario.github.io/nome-do-repo/`.

## Primeiro uso

1. Abra o link publicado.
2. Vá em **Configurações** na lateral, cole sua chave da API Anthropic (pegue em console.anthropic.com, seção API Keys) e salve.
3. Crie um cliente clicando no `+` ao lado de "Clientes".
4. Revise os frameworks em **Frameworks**: já vêm dois modelos prontos (Demonstração comercial e Checklist de forecast) além do SPIN Selling fixo, todos editáveis exceto o SPIN. Ajuste os itens pro roteiro real do seu cliente, ou crie frameworks novos do zero.
5. Clique em **Nova auditoria**, escolha o cliente, marque os frameworks aplicáveis àquela call, suba ou cole a transcrição literal completa, e analise.

## Organização

- **Clientes**: cada cliente tem sua própria pasta de calls na lateral. Renomeia e exclui pelos ícones que aparecem ao passar o mouse.
- **Calls**: renomeável e excluível tanto na lateral quanto dentro do próprio relatório.
- **Frameworks**: crie quantos quiser, com itens e pesos próprios. Um framework excluído não apaga as calls que já foram avaliadas com ele, só deixa de aparecer nas próximas.
- **Ranking**: lista todas as calls ordenadas por aderência, com filtro por cliente e por vendedor.

## Aviso de segurança

A chave de API fica salva apenas no localStorage do navegador de quem estiver usando a página, e as chamadas vão direto do navegador para a API da Anthropic. Isso é adequado pra uso pessoal ou de um time pequeno e de confiança, cada pessoa com sua própria chave. Não distribua sua chave pra outras pessoas usarem no mesmo link. Se o repositório for público, qualquer pessoa pode abrir o app e usar com a própria chave dela, mas ninguém vê a sua.

Os dados (clientes, frameworks, calls, transcrições) também ficam só no localStorage: são por navegador e por computador, não sincronizam entre dispositivos e são perdidos se você limpar os dados do site.
