# Configuração do AeroSpace 🚀

Este repositório contém a configuração personalizada do [AeroSpace](https://github.com/nikitabobko/AeroSpace), um gerenciador de janelas em árvore (tiling window manager) para macOS inspirado no i3wm.

## 📑 Índice

- [Instalação](#instalação)
- [Configurações Principais](#configurações-principais)
- [Layouts](#layouts)
- [Workspaces](#workspaces)
- [Atalhos de Teclado](#atalhos-de-teclado)
- [Integração com SketchyBar](#integração-com-sketchybar)
- [Configuração de Monitores](#configuração-de-monitores)
- [Modo Service](#modo-service)

## 🔧 Instalação

1. **Instale o AeroSpace:**
   ```bash
   brew install --cask nikitabobko-aerospace
   ```

2. **Copie a configuração:**
   ```bash
   cp .aerospace.toml ~/.aerospace.toml
   ```

3. **Reinicie o AeroSpace:**
   - Feche o AeroSpace se estiver rodando
   - Abra o AeroSpace novamente
   - Ou use o atalho `Alt + Shift + ;` seguido de `Esc` para recarregar a configuração

## ⚙️ Configurações Principais

### Normalização
- **Flatten Containers**: Ativado - Remove containers desnecessários
- **Opposite Orientation**: Ativado - Otimiza orientação de containers aninhados

### Layouts
- **Layout Padrão**: `tiles` (azulejos)
- **Orientação Padrão**: `auto` (automática baseada na proporção do monitor)
- **Accordion Padding**: 30px - Espaçamento para o layout accordion

### Gaps (Espaços)
- **Gaps Internos**: 10px (horizontal e vertical)
- **Gaps Externos**: 10px (todas as direções)

### Comportamentos
- **Start at Login**: Desabilitado
- **Mouse Follows Focus**: Ativado
- **Auto-unhide Apps**: Desabilitado

## 🎨 Layouts

### Tiles (Azulejos)
Layout padrão onde as janelas são organizadas em grades lado a lado.

### Accordion (Acordeon)
Layout onde uma janela ocupa a maior parte do espaço e as outras ficam minimizadas na lateral.

**Alternar entre layouts:**
- `Alt + /`: Alternar tiles horizontal/vertical
- `Alt + ,`: Alternar accordion horizontal/vertical

## 🏢 Workspaces

Esta configuração oferece 35 workspaces diferentes:

### Numéricos (1-9)
Workspaces numerados de 1 a 9 para organização básica.

### Alfabéticos (A-Z)
Workspaces com letras de A a Z (exceto H, J, K, L que são usados para navegação).

**Workspaces disponíveis:**
`1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F, G, I, M, N, O, P, Q, R, S, T, U, V, W, X, Y, Z`

## ⌨️ Atalhos de Teclado

### Navegação entre Janelas
| Atalho | Ação |
|--------|------|
| `Alt + H` | Focar janela à esquerda |
| `Alt + J` | Focar janela abaixo |
| `Alt + K` | Focar janela acima |
| `Alt + L` | Focar janela à direita |

### Movimentação de Janelas
| Atalho | Ação |
|--------|------|
| `Alt + Shift + H` | Mover janela para esquerda |
| `Alt + Shift + J` | Mover janela para baixo |
| `Alt + Shift + K` | Mover janela para cima |
| `Alt + Shift + L` | Mover janela para direita |

### Redimensionamento
| Atalho | Ação |
|--------|------|
| `Alt + -` | Diminuir tamanho da janela (50px) |
| `Alt + =` | Aumentar tamanho da janela (50px) |

### Navegação entre Workspaces
| Atalho | Workspace |
|--------|-----------|
| `Alt + 1-9` | Ir para workspace numérico |
| `Alt + A-Z` | Ir para workspace alfabético |
| `Alt + Tab` | Alternar entre último workspace |

### Mover Janelas entre Workspaces
| Atalho | Ação |
|--------|------|
| `Alt + Shift + 1-9` | Mover janela para workspace numérico |
| `Alt + Shift + A-Z` | Mover janela para workspace alfabético |
| `Alt + Shift + Tab` | Mover workspace para próximo monitor |

### Controles de Layout
| Atalho | Ação |
|--------|------|
| `Alt + /` | Alternar layout tiles |
| `Alt + ,` | Alternar layout accordion |

### Modo Service
| Atalho | Ação |
|--------|------|
| `Alt + Shift + ;` | Entrar no modo service |

## 📊 Integração com SketchyBar

A configuração inclui integração automática com o SketchyBar para mostrar o workspace ativo:

```toml
exec-on-workspace-change = [
    '/bin/bash',
    '-c',
    'sketchybar --trigger aerospace_workspace_change FOCUSED_WORKSPACE=$AEROSPACE_FOCUSED_WORKSPACE',
]
```

Toda vez que você trocar de workspace, o SketchyBar será notificado automaticamente.

## 🖥️ Configuração de Monitores

### Monitor Interno (Built-in Retina Display)
Workspaces assignados: `1, 2, 3, 4, 5`

### Monitor Externo (27G2G4)
Workspaces assignados: `Q, W, E, R`

Esta configuração força certos workspaces a sempre aparecerem em monitores específicos, mantendo uma organização consistente em setups multi-monitor.

## 🛠️ Modo Service

O modo service (`Alt + Shift + ;`) oferece comandos avançados:

| Atalho (no modo service) | Ação |
|-------------------------|------|
| `Esc` | Recarregar configuração e voltar ao modo main |
| `R` | Reset do layout (flatten) e voltar ao modo main |
| `F` | Alternar entre floating e tiling |
| `Backspace` | Fechar todas as janelas exceto a atual |
| `Alt + Shift + H/J/K/L` | Juntar janela com direção especificada |
| `↓` | Diminuir volume |
| `↑` | Aumentar volume |
| `Shift + ↓` | Mutar volume |

## 📚 Recursos Adicionais

- **Documentação Oficial**: https://nikitabobko.github.io/AeroSpace/
- **Comandos Disponíveis**: https://nikitabobko.github.io/AeroSpace/commands
- **Guia de Configuração**: https://nikitabobko.github.io/AeroSpace/guide

## 🤝 Contribuição

Sinta-se livre para fazer fork deste repositório e adaptar a configuração às suas necessidades. Se encontrar melhorias úteis, pull requests são bem-vindos!

## 📄 Licença

Este arquivo de configuração é distribuído sob a mesma licença do AeroSpace.
