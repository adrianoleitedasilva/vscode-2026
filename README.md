## VS Code — Explicação Detalhada das Configurações

![Visual Studio Code](https://img.shields.io/badge/Visual%20Studio%20Code-0078d7.svg?style=for-the-badge&logo=visual-studio-code&logoColor=white) ![Json File](https://img.shields.io/badge/Json_ConfigFile-D32936.svg?style=for-the-badge&logo=tools&logoColor=white) ![Estudo](https://img.shields.io/badge/Estudo-1a1a1a?style=for-the-badge&logo=quicklook&logoColor=white)

Este documento descreve, de forma detalhada e prática, as configurações utilizadas no arquivo `settings.json` do Visual Studio Code, explicando **o que cada opção faz** e **qual o impacto visual ou funcional no editor**.

---

## 1. Workbench (Interface Geral do VS Code)

```json
"workbench.productIconTheme": "fluent-icons"
```

Define o tema de ícones internos do VS Code (ícones de ações, painéis e elementos nativos).
O tema Fluent Icons segue o padrão visual Fluent Design da Microsoft, deixando a interface mais moderna e consistente.

```json
"workbench.colorTheme": "Min Dark"
```
Define o tema de cores global do VS Code, incluindo fundo do editor, cores da interface e realce de sintaxe.
O tema Min Dark oferece um visual escuro e minimalista, focado em reduzir distrações.

```json
"workbench.iconTheme": "material-icon-theme"
```
Define o tema de ícones exibidos no Explorer (árvore de arquivos e pastas).
O Material Icon Theme fornece ícones específicos para cada tipo de arquivo, melhorando a identificação visual do projeto.

```json
"workbench.sideBar.location": "right"
```
Move a barra lateral (Explorer, Search, Source Control) para o lado direito da tela.
Útil para quem prefere manter o código mais próximo do lado esquerdo ou trabalha com monitores ultrawide.

```json
"workbench.activityBar.location": "top"
```
Move a Activity Bar (ícones de Explorer, Search, Git, Extensions) para o topo da interface, reduzindo ocupação lateral.

```json
"workbench.startupEditor": "newUntitledFile"
```
Ao iniciar o VS Code, abre diretamente um novo arquivo em branco, em vez da tela de boas-vindas ou arquivos recentes.

```json
"workbench.editor.labelFormat": "short"
```
Define o formato do nome exibido nas abas do editor.
O modo short prioriza nomes mais curtos, evitando excesso de texto nas tabs.

```json
"workbench.statusBar.visible": false
```
Oculta a Status Bar (barra inferior), removendo informações como branch do Git, encoding e posição do cursor.
Gera um visual mais limpo, porém com menos feedback visual imediato.

```json
"workbench.layoutControl.enabled": false
```
Desativa os controles visuais rápidos de layout do VS Code, reduzindo elementos na interface.

## 2. Editor de Código

```json
"editor.cursorSmoothCaretAnimation": "on"
```
Ativa animações suaves ao mover o cursor, tornando a navegação mais fluida.

```json
"editor.cursorBlinking": "smooth"
```
Desativa o minimapa do código, liberando espaço horizontal e reduzindo distrações visuais.

```json
"editor.fontFamily": "JetBrains Mono"
```
Define a fonte principal do editor.
A JetBrains Mono é otimizada para código, com excelente legibilidade.


```json
"editor.fontLigatures": true
```
Ativa ligaturas tipográficas, transformando combinações como =>, != e === em símbolos visuais mais elegantes.

```json
"editor.fontSize": 16
```
Define o tamanho da fonte do editor, favorecendo conforto visual.

```json
"editor.lineHeight": 1.6
```
Aumenta o espaçamento vertical entre linhas, deixando o código mais arejado e legível.

```json
"editor.rulers": [90, 120]
```
Exibe linhas-guia verticais nas colunas 90 e 120, auxiliando no controle de largura de linhas conforme padrões de código.

```json
"editor.renderLineHighlight": "gutter"
```
Destaca a linha atual apenas no gutter (região dos números de linha), mantendo o destaque discreto.

```json
"editor.semanticHighlighting.enabled": false
```
Desativa o realce semântico baseado em linguagem, mantendo apenas o destaque fornecido pelo tema.

```json
"editor.scrollbar.horizontal": "hidden"
"editor.scrollbar.vertical": "hidden"
```
Oculta a barra de rolagem horizontal, contribuindo para um visual mais limpo. 
Oculta a barra de rolagem vertical, mantendo apenas a rolagem por mouse, teclado ou touchpad.

## 3. Navegação e Comandos

```json
"breadcrumbs.enabled": false
```
Desativa os breadcrumbs (caminho do arquivo e símbolos no topo do editor), reduzindo elementos visuais.


```json
"window.commandCenter": false
```
Remove o Command Center da interface superior.
Os comandos continuam acessíveis via Ctrl + Shift + P.

## 4. Explorer (Árvore de Arquivos)

```json
"explorer.compactFolders": false
```
Desativa a compactação automática de pastas com apenas um nível, exibindo toda a hierarquia explicitamente.

```json
"explorer.fileNesting.enabled": true
```
Ativa o agrupamento de arquivos relacionados no Explorer, reduzindo poluição visual.

```json
"explorer.fileNesting.patterns": {
  "*.ts": "${capture}.js",
  "*.js": "${capture}.js.map, ${capture}.min.js, ${capture}.d.ts",
  "*.jsx": "${capture}.js",
  "*.tsx": "${capture}.ts",
  "tsconfig.json": "tsconfig.*.json",
  "package.json": "yarn.lock*, .eslint*, prettier*, tsconfig*, vite*, pnpm-lock*, package-lock*, bun.lock*",
  ".env.local": ".env*",
  ".env": ".env*"
}
```

Define regras de aninhamento de arquivos derivados, como:

- arquivos compilados
- arquivos de configuração
- lockfiles
- variações de .env

Isso mantém o Explorer mais organizado e focado nos arquivos principais.

## 5. Terminal Integrado

```json
"terminal.integrated.fontSize": 15
```
Define o tamanho da fonte do terminal integrado.

```json
"terminal.integrated.fontFamily": "JetBrains Mono"
```
Mantém a mesma fonte do editor no terminal, garantindo consistência visual.

```json
"terminal.integrated.fontLigatures.enabled": true
```
Ativa ligaturas tipográficas no terminal, quando suportadas pela fonte.

```json
"terminal.integrated.lineHeight": 1.2
```
Ajusta o espaçamento vertical das linhas no terminal, tornando-o mais compacto.
