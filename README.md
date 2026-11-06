# Skill do Claude – Orçamento GSF

Skill que analisa uma solicitação de orçamento do **Grupo SF**. Ela pede a pasta do orçamento, lê os documentos da subpasta **Recebidos** (PDFs, plantas, planilhas, e-mails) e gera na própria pasta:

1. **Resumo Técnico Interno** (Word + PDF): escopo, riscos, premissas e exclusões, só para uso interno.
2. **Questionário Técnico / Elucidação** (Word + PDF): dúvidas numeradas para enviar ao cliente.
3. **Planilha de Custos e Materiais** (.xlsx): custo estimado e preço de venda (custo ÷ 0,70).
4. **Proposta Técnica** (Word + PDF)
5. **Proposta Comercial** (Word + PDF)

A skill também gera a revisão (Rev.01) quando o cliente responde ou pede ajustes.

## Como instalar

### No Claude (site claude.ai ou app Claude Desktop)

1. Baixe o arquivo **`orcamento-gsf.zip`** deste repositório: clique no arquivo e depois em **Download raw file** (ícone de download).
2. No Claude, verifique se a execução de código está ativada em **Configurações → Capacidades** (*Settings → Capabilities*).
3. Abra **Personalizar → Skills** (*Customize → Skills*).
4. Clique em **+** → **Criar skill** → **Enviar uma skill** (*Upload a skill*) e selecione o `orcamento-gsf.zip`.
5. Confira se a skill **orcamento-gsf** aparece na lista e está ativada.

> Custom skills exigem plano Pro, Max, Team ou Enterprise. Em planos Team/Enterprise, o administrador precisa ter liberado Skills nas configurações da organização.

### No Claude Code

Copie a pasta `orcamento-gsf/` para `~/.claude/skills/` (skill pessoal) ou para `.claude/skills/` dentro do projeto.

## Como usar

1. Para ler e salvar arquivos no seu computador, use o **app Claude Desktop** e libere a pasta quando o Claude pedir acesso.
2. Digite `/orcamento-gsf` ou peça: *"faça a análise de orçamento GSF"*.
3. Cole o caminho completo da pasta do orçamento quando o Claude perguntar, por exemplo:
   `C:\Users\<usuario>\OneDrive\Documentos\Dados\Modelos_Orçamentos\Modelo Obras\Propostas_Criadas\1234 - Cliente Serviço`
4. A pasta precisa ter uma subpasta **Recebidos** (ou **Recebido**) com os documentos do cliente.
5. Se o nome da pasta começar com o número da proposta, esse número é usado nos arquivos. Caso contrário, fica "XXXX".

## Observações

- Os preços da planilha são **estimativas**. Confirme os valores com cotações de fornecedores antes de enviar a proposta.
- Os dados da empresa e do responsável técnico estão no `SKILL.md` (Passos 6 e 7). Para alterar, edite o arquivo, gere o zip de novo e reenvie a skill.

## Conteúdo do repositório

```
orcamento-gsf/
└── SKILL.md          # instruções da skill
orcamento-gsf.zip     # pacote pronto para enviar no Claude
README.md
```
