---
name: "orcamento-gsf"
description: "Análise de solicitação de orçamento do Grupo SF: pede a pasta, lê os documentos recebidos e gera resumo técnico, questionário, planilha de custos, proposta técnica e comercial."
---

# Orçamento GSF – análise de solicitação de orçamento

Responder sempre em português. Propostas sempre em nome do Grupo SF.

## Passo 1 – Perguntar a pasta (SEMPRE o primeiro passo)

Antes de qualquer outra ação, enviar ao usuário esta mensagem (adaptando só o necessário):

> Qual pasta devo analisar? Cole o caminho completo (ex.: `C:\Users\nilso\OneDrive\Documentos\Dados\Modelos_Orçamentos\Modelo Obras\Propostas_Criadas\XXXX - Cliente Serviço`).
>
> Depois da análise da pasta (subpasta **Recebidos**), vou gerar, em Word e PDF, na própria pasta:
> 1. **Resumo Técnico Interno** – o que o cliente quer, escopo, riscos, premissas e exclusões (só para você)
> 2. **Questionário Técnico / Elucidação** – dúvidas numeradas para enviar ao cliente
> 3. **Planilha de Custos e Materiais** (.xlsx) – custo estimado e preço de venda (fator 0,70)
> 4. **Proposta Técnica**
> 5. **Proposta Comercial**
>
> Se a pasta tiver número de proposta no nome, uso esse número; senão fica "XXXX".

Esperar o usuário colar o caminho. Não começar antes.

## Passo 2 – Acesso e leitura

- Pedir acesso à pasta informada (device_request_folder_access), listar recursivamente e trazer para o workspace todos os arquivos da subpasta **Recebidos** (ou da pasta, se não houver Recebidos).
- Ler tudo: PDFs (texto e páginas como imagem quando houver plantas), .doc/.docx, planilhas, e-mails (.msg/.eml/.txt), imagens.
- Anotar: cliente, unidade, endereço, contato, escopo pedido, quantidades, especificações, normas, prazos de entrega da proposta e da obra, condições de execução (horário, ICRA, segurança), exigências especiais.
- Separar o que está faltando, contraditório ou ambíguo.
- Se o cliente já tem proposta anterior do Grupo SF ou modelo aprovado (ex.: G:\Meu Drive\a-ASF\03 - Clientes\<cliente>), usar como referência de formato e preço.

## Passo 3 – Resumo Técnico Interno (uso interno)

- O que o cliente quer em poucas linhas.
- Escopo item a item com quantidades.
- Riscos e pontos que encarecem (içamento, horário noturno/fim de semana, interferências, prazos, exigências de terceiros).
- Premissas adotadas e exclusões.
- Itens que dependem de resposta do questionário.

## Passo 4 – Questionário Técnico / Elucidação (para o cliente)

- Perguntas numeradas Q1, Q2… cada uma com referência ao documento/item de origem.
- Objetivo: eliminar ambiguidade antes de fechar preço.
- Declaração final do responsável técnico.

## Passo 5 – Planilha de Custos e Materiais (.xlsx, interna)

- Abas por grupo: materiais, equipamentos, mão de obra, terceiros (guindaste/Munck, TAB, projetos/ART, laboratório), despesas (alimentação, transporte, caçambas, EPIs).
- Fórmulas no Excel (não valores fixos). Preço de venda = custo ÷ 0,70.
- Resumo por item C.1…C.n que alimenta a proposta comercial.

## Passo 6 – Proposta Técnica

- Dados do cliente, referência aos documentos recebidos, número, data, revisão (00), validade.
- Escopo por disciplina: projetos e ART, desmontagem, equipamentos, hidráulica, dutos, automação/controle, elétrica, transporte/içamento, testes, TAB e comissionamento, documentação/as built.
- Lista de equipamentos, premissas, responsabilidades do cliente, exclusões, cronograma, condições de execução.
- Responsável técnico: Sérgio Silveira de Carvalho, Técnico em Refrigeração, CFT nº 260395801-1.

## Passo 7 – Proposta Comercial

- Tabela de itens C.1…C.n com valores, total e **valor global por extenso**; impostos inclusos.
- Cronograma de pagamento (ex.: 30 % pedido / 50 % medições / 20 % entrega).
- Preços unitários para acréscimos, opcionais, validade, prazo, condições.
- Dados da empresa: Grupo SF – A. de S. N. Carvalho Refrigeração – ME, CNPJ 28.746.353/0001-54, Rua Alfredo Batista Pizolato, 69 – Suzano/SP, gruposf@gruposf.ind.br, (11) 4748-5453.
- Local e data: "Suzano, <data>".

## Passo 8 – Entrega

- Gerar .docx e .pdf de cada documento (planilha em .xlsx), conferir o PDF renderizado (páginas, tabelas, sem texto sobrando de modelo).
- Salvar na pasta informada, com nomes no padrão: `<Documento> - <nº> - <Cliente> - <Serviço>`.
- Verificar com device_list_dir que os arquivos estão lá (tamanho > 0); se não, gravar de novo com force.
- Responder com resumo curto: valor global, principais premissas/riscos e as perguntas mais importantes do questionário.

## Revisão (quando o cliente responder ou pedir ajuste)

- Gerar **Resumo da Revisão**: tabela item do cliente × já está na proposta? × o que muda × impacto no valor; cenários de preço A/B/C.
- Após a decisão do usuário, gerar **Rev.01** da técnica e da comercial, sem apagar a Rev.00 (nome com "- Rev01").