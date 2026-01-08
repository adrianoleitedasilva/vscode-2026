Workbench (interface do VS Code)
"workbench.productIconTheme": "fluent-icons"

Define o tema de ícones “do produto” (ícones nativos do VS Code: arquivos básicos, ações, views).

Na prática: muda o “visual padrão” de vários ícones do VS Code para o pacote Fluent (estilo Microsoft).

Observação: isso é diferente do workbench.iconTheme (que afeta ícones do Explorer).

"workbench.colorTheme": "Min Dark"

Define o tema de cores geral do editor/IDE (fundo, cores de syntax highlighting, UI, etc.).

Na prática: muda o esquema de cores para o tema chamado Min Dark (precisa estar instalado).

"workbench.iconTheme": "material-icon-theme"

Define o tema de ícones do Explorer (pastas/arquivos na árvore do projeto).

Na prática: arquivos .js, .ts, package.json, etc. ganham ícones específicos do Material Icon Theme.

É o que você mais “vê” na lateral ao navegar no projeto.

"workbench.sideBar.location": "right"

Move a Side Bar (Explorer, Search, Source Control) para a direita.

Padrão: esquerda.

Útil para quem quer o código “começando” mais à esquerda (ou usa monitor ultrawide e prefere painel à direita).

"workbench.activityBar.location": "top"

Move a Activity Bar (a barra com ícones: Explorer, Search, Git, Extensions) para o topo.

Padrão: lateral esquerda.

Deixa a UI mais “compacta” nas laterais.

"workbench.startupEditor": "newUntitledFile"

Ao abrir o VS Code, em vez de mostrar “Welcome / Recent”, ele abre um arquivo novo sem título.

Na prática: abre direto um editor vazio para você começar a digitar.

"workbench.editor.labelFormat": "short"

Controla como o VS Code mostra o “nome” das abas do editor.

short: tende a mostrar só o nome do arquivo (ex.: index.ts) e resolve conflitos de nomes iguais de forma mais simples.

Ajuda a deixar as tabs mais limpas.

"workbench.statusBar.visible": false

Esconde a Status Bar (barra inferior com branch, erros, encoding, line/col, etc.).

Na prática: ganha espaço vertical e um visual mais “clean”.

Trade-off: você perde informação rápida (Git branch, problemas, etc.).

"workbench.layoutControl.enabled": false

Desativa o controle de layout (o “botão/controle” que facilita mudar layout pela UI).

Na prática: menos elementos visuais e menos “atalhos” de layout na interface.

Você ainda pode mudar layout por menu/atalhos, só não fica “exposto” no UI.

Editor (comportamento do editor de código)
"editor.cursorSmoothCaretAnimation": "on"

Ativa animação suave ao mover o cursor (caret).

Na prática: ao navegar com setas, mouse, etc., o cursor “desliza” suavemente.

"editor.cursorBlinking": "smooth"

Define o modo de “piscar” do cursor como suave.

Na prática: a animação do cursor fica menos “seca” e mais fluida.

"editor.minimap.enabled": false

Desativa o minimap (mini mapa do código do lado direito).

Na prática: ganha espaço lateral e reduz distração.

Trade-off: perde navegação visual rápida por trechos.

"editor.fontFamily": "JetBrains Mono"

Define a fonte principal do editor como JetBrains Mono.

Na prática: muda legibilidade, espaçamento e aparência do código.

Precisa estar instalada no sistema.

"editor.fontLigatures": true

Ativa ligaturas tipográficas (combinações visuais, tipo =>, !=, === virarem símbolos mais “bonitos”).

Na prática: o texto continua o mesmo, é só renderização.

Bom para quem gosta de estética/legibilidade; alguns preferem desligado.

"editor.fontSize": 16

Tamanho da fonte do editor em 16px.

Na prática: melhora leitura (especialmente em monitores maiores).

"editor.lineHeight": 1.6

Altura da linha (espaçamento vertical) como multiplicador.

Na prática: código fica mais “arejado” (menos poluído visualmente).

Pode reduzir a quantidade de linhas visíveis por tela.

"editor.rulers": [90, 120]

Mostra linhas-guia verticais nas colunas 90 e 120.

Na prática: ajuda a manter largura de linha consistente (padrões de estilo).

Ex.: “evitar linhas >120” e “ideal ~90”.

"editor.renderLineHighlight": "gutter"

Destaca a linha atual apenas no gutter (a “faixa” onde ficam números de linha/marcadores), não a linha inteira.

Na prática: destaque mais discreto, menos “faixa luminosa” no código.

"editor.semanticHighlighting.enabled": false

Desativa highlight semântico (cores baseadas no significado do símbolo via Language Server).

Na prática: o VS Code não muda cor por “tipo real” (classe, interface, parâmetro, etc.) além do que o tema faz.

Motivos comuns: preferir o tema “puro”, evitar inconsistências entre linguagens, ou reduzir ruído.

"editor.scrollbar.horizontal": "hidden"

Esconde a barra de rolagem horizontal.

Na prática: visual mais clean.

Você ainda pode rolar horizontalmente (trackpad/Shift+scroll), mas sem barra visível.

"editor.scrollbar.vertical": "hidden"

Esconde a barra de rolagem vertical.

Mesmo efeito: menos UI aparente, rolagem continua possível.

Navegação e comandos
"breadcrumbs.enabled": false

Desativa breadcrumbs (a trilha no topo do editor: src > components > Button.tsx).

Na prática: remove uma linha da UI e reduz distração.

Trade-off: perde navegação rápida por estrutura/arquivo.

"window.commandCenter": false

Desativa o Command Center (um elemento/atalho visual na barra superior para comandos/pesquisa).

Na prática: menos itens na barra do topo, UI mais minimalista.

Você ainda tem Ctrl+Shift+P (Command Palette).

Explorer (árvore de arquivos)
"explorer.compactFolders": false

Desativa “compactação” de pastas com único filho.

Com false: src/components/button aparece em níveis separados.

Com true: pode aparecer como src/components/button numa “linha só”.

Quem desliga geralmente quer ver a hierarquia explicitamente.

"explorer.fileNesting.enabled": true

Ativa aninhamento de arquivos no Explorer (arquivos “relacionados” ficam agrupados).

Na prática: arquivos derivados (map, min, d.ts, etc.) ficam “dentro” do arquivo principal.

"explorer.fileNesting.patterns": { ... }

Define as regras de aninhamento. O lado esquerdo é o “pai” e o lado direito são os “filhos” que serão agrupados.

"*.ts": "${capture}.js"
Para um arquivo.ts, o Explorer vai tentar aninhar arquivo.js embaixo dele (quando existir).

"*.js": "${capture}.js.map, ${capture}.min.js, ${capture}.d.ts"
Para arquivo.js, ele aninha:

arquivo.js.map (source map)

arquivo.min.js (build minificado)

arquivo.d.ts (tipos TypeScript gerados)

"*.jsx": "${capture}.js"
Para arquivo.jsx, aninha arquivo.js (muitas ferramentas geram .js a partir de JSX).

"*.tsx": "${capture}.ts"
Para arquivo.tsx, aninha arquivo.ts (pode ocorrer em builds/estruturas específicas).

"tsconfig.json": "tsconfig.*.json"
Aninha tsconfig.app.json, tsconfig.node.json, etc. dentro do tsconfig.json.

"package.json": "yarn.lock*, .eslint*, prettier*, tsconfig*, vite*, pnpm-lock*, package-lock*, bun.lock*"
Dentro do package.json, aninha itens comuns de projeto:

lockfiles (yarn.lock, pnpm-lock.yaml, package-lock.json, bun.lock*)

configs (.eslintrc*, prettier*, tsconfig*, vite*)

O * indica “qualquer variação” (ex.: .eslintrc.json, .eslintrc.cjs, etc.)

".env.local": ".env*" e ".env": ".env*"
Agrupa arquivos .env relacionados (ex.: .env.development, .env.production, .env.local).

Resultado geral: Explorer mais organizado, reduz “poluição” de arquivos derivados.

Terminal integrado
"terminal.integrated.fontSize": 15

Tamanho da fonte do terminal em 15px.

"terminal.integrated.fontFamily": "JetBrains Mono"

Fonte do terminal também em JetBrains Mono (consistência visual com o editor).

"terminal.integrated.fontLigatures.enabled": true

Liga ligaturas no terminal.

Na prática: alguns símbolos podem renderizar com ligaturas (se a fonte suportar).

"terminal.integrated.lineHeight": 1.2

Ajusta espaçamento vertical no terminal.

1.2 deixa o terminal mais “compacto” que o editor (que está 1.6).
