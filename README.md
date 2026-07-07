[README (1).md](https://github.com/user-attachments/files/29755735/README.1.md)
# Playbook de Gestão — Clínicas

Sistema web de gestão de tarefas (estilo kanban/lista) voltado para o acompanhamento
mensal de processos operacionais (BPO) de clínicas. Permite cadastrar clínicas,
organizar tarefas por mês, mover tarefas entre etapas (Backlog → Em Análise →
Em Andamento → Revisão → Concluído), adicionar subtarefas, responsáveis,
prioridades, prazos e anexos.

## ✨ Funcionalidades

- Cadastro de múltiplas clínicas (abas na barra lateral).
- Organização de tarefas por mês (seletor de mês).
- Duas visualizações: **Lista** e **Kanban**.
- Subtarefas com barra de progresso.
- Prioridades (alta/média/baixa), responsável e prazo por tarefa.
- Anexos de arquivos por tarefa.
- Modal de detalhes da tarefa (edição completa).
- Persistência local dos dados via `localStorage` (dados da aplicação) e
  `IndexedDB` (arquivos anexados) — nenhum dado é enviado a um servidor.

## 📁 Estrutura de arquivos

```
projeto/
├── index.html
├── style.css
├── script.js
├── README.md
└── assets/
    └── fonts/
        ├── Inter-Light.woff2 / .woff
        ├── Inter-Regular.woff2 / .woff
        ├── Inter-Medium.woff2 / .woff
        ├── Inter-SemiBold.woff2 / .woff
        └── Inter-Bold.woff2 / .woff
```

> ⚠️ Os arquivos de fonte **não estão incluídos**. O CSS já contém as regras
> `@font-face` apontando para `assets/fonts/`, prontas para você substituir
> pelos arquivos reais da fonte Inter (ou de outra fonte de sua escolha,
> bastando ajustar os nomes dos arquivos).

## 🚀 Como executar

Este é um projeto 100% estático (HTML + CSS + JS puro, sem build ou dependências
de backend). Para rodar:

1. Baixe/clone os arquivos mantendo a estrutura de pastas acima.
2. Coloque os arquivos de fonte reais dentro de `assets/fonts/`.
3. Abra o arquivo `index.html` diretamente no navegador **ou**, para evitar
   eventuais bloqueios de segurança do navegador com `IndexedDB`/anexos,
   sirva a pasta com um servidor local simples, por exemplo:

   ```bash
   # Python 3
   python3 -m http.server 8000
   ```

   Depois acesse `http://localhost:8000` no navegador.

## 💾 Armazenamento de dados

- As informações das clínicas, tarefas e progresso são salvas no
  `localStorage` do navegador.
- Os arquivos anexados às tarefas são salvos no `IndexedDB` do navegador.
- **Os dados são locais ao navegador/dispositivo** — ao abrir o sistema em
  outro computador ou navegador, os dados não estarão disponíveis, pois não
  há sincronização com nenhum servidor.

## 🛠️ Tecnologias

- HTML5
- CSS3 (variáveis CSS, grid, flexbox, responsivo)
- JavaScript puro (Vanilla JS — sem frameworks ou bibliotecas externas)
