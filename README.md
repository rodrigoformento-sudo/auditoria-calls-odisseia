# Auditoria de Calls · Odisseia

App de auditoria de calls comerciais (Roteiro Demo, SPIN Selling e checklist A Montanha), com veredito por item, evidência obrigatória e histórico local.

Essa é a versão standalone, sem depender do claude.ai. Ela chama a API da Anthropic direto do navegador usando a sua própria chave de API.

## Como publicar no GitHub Pages

1. Crie um repositório novo no GitHub (pode ser privado ou público, ver aviso de segurança abaixo).
2. Suba o arquivo `index.html` deste pacote pra raiz do repositório.
3. No repositório, vá em **Settings > Pages**.
4. Em **Source**, escolha **Deploy from a branch**, branch `main`, pasta `/ (root)`.
5. Salve. Em alguns minutos o GitHub te dá o link, algo como `https://seu-usuario.github.io/nome-do-repo/`.

Pronto, é isso. Não tem build, não tem dependência de instalar nada, é só o HTML.

## Como usar

1. Abra o link publicado.
2. Cole sua chave da API Anthropic no campo da lateral esquerda e clique em Salvar (pegue a chave em console.anthropic.com, seção API Keys).
3. Preencha cliente, vendedor, data e o framework da call.
4. Suba o arquivo da transcrição (.txt, .md ou .docx) ou cole o texto direto.
5. Clique em Analisar call.

O histórico de calls auditadas fica salvo no navegador (localStorage), não em nenhum servidor.

## Aviso de segurança importante

Esse app chama a API da Anthropic diretamente do navegador de quem estiver usando a página. Isso significa:

- A chave de API fica salva **apenas no localStorage do navegador de cada pessoa**, nunca é escrita no código nem enviada pra nenhum lugar além da Anthropic.
- Só que, por ser uma chamada client side, qualquer pessoa com acesso ao link e disposta a abrir o DevTools do navegador consegue ver a chave que ela mesma digitou (a dela, não a de outras pessoas). Isso é aceitável pra uso pessoal ou de um time pequeno e de confiança, cada um com sua própria chave.
- **Não distribua sua própria chave pra outras pessoas usarem nesse link.** Se quiser que o time inteiro use, cada pessoa deve ter e cadastrar a própria chave da Anthropic.
- Se o repositório for público, qualquer pessoa pode abrir o link e usar o app (com a própria chave dela), mas ninguém vê a sua. Se isso for um problema, deixe o repositório e o Pages como privados (exige GitHub Pro/Team/Enterprise pra Pages privado) ou restrinja o acesso por outros meios.

## Diferenças em relação à versão que roda dentro do claude.ai

- Aqui a análise usa sua própria chave de API e é cobrada diretamente na sua conta Anthropic, por uso.
- O histórico é local ao navegador (some se você limpar os dados do site ou trocar de navegador/computador), não é compartilhado entre pessoas.
- Fora isso, os critérios de auditoria, o cálculo de placar e o layout são idênticos à versão hospedada no claude.ai.
