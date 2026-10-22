# GitHub Actions — Automações do Repositório

## Sobre o projeto

Este repositório utiliza GitHub Actions para automatizar tarefas de desenvolvimento, gerar documentação e disponibilizar versões do projeto para download.

Os workflows são definidos em arquivos YAML localizados na pasta `.github/workflows/`.

## Workflows

### 1. `teste.yml` — Hello World

**Objetivo:** demonstrar o funcionamento básico do GitHub Actions.

O workflow executa um comando que exibe a mensagem `Hello World!` no terminal da máquina virtual do GitHub Actions.

Essa automação serve como exemplo introdutório para entender a execução de comandos e o funcionamento dos workflows.

### 2. `changelog.yml` — Histórico de alterações

**Objetivo:** gerar e atualizar automaticamente o arquivo `CHANGELOG.md`.

O workflow:
- É executado quando há um `push` para a branch `main` ou quando iniciado manualmente.
- Consulta os 20 commits mais recentes, excluindo commits de merge.
- Registra as datas, mensagens, identificadores e autores dos commits.
- Exibe o changelog no resumo da execução.
- Salva as alterações no repositório quando necessário.

### 3. `release.yml` — Compactação das versões

**Objetivo:** gerar um arquivo ZIP para cada Release publicada.

O workflow:
- É acionado quando uma Release é publicada no GitHub.
- Baixa o código correspondente à tag da versão.
- Compacta os arquivos versionados em um arquivo ZIP.
- Anexa o ZIP à Release correspondente.

O arquivo fica disponível para download na seção **Releases → Assets**.


## Estrutura do projeto

```text
.github/
└── workflows/
    ├── blank.yml
    ├── changelog.yml
    ├── release.yml
    └── teste.yml
```

## Como acompanhar as execuções

1. Acesse a aba **Actions** do repositório.
2. Selecione o workflow desejado.
3. Abra uma execução para consultar suas etapas e os registros de execução.
4. Verifique se a execução terminou com sucesso.

Para baixar uma versão compactada, acesse **Releases**, abra a versão desejada e procure o arquivo ZIP na seção **Assets**.

## Conclusão

Essas automações demonstram recursos do GitHub Actions, desde a execução de um comando simples até a geração automática de documentação e a distribuição de versões compactadas do projeto.
