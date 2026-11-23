# TAREFA — página de teste de procura "Raio-X do Imóvel"

[Projeto: raio-x-imovel]

## Objetivo
Montar UMA página estática (um único `index.html`, com CSS e JS dentro dele) para testar se alguém clica para pedir um relatório de triagem de imóvel da Caixa. É teste de procura, não produto: nada de backend, cadastro, pagamento real ou framework.

## Regras que não se discutem
- Trabalhar só dentro de `~/Projetos/raio-x-imovel`. Pode rodar `git init` AQUI (nunca em `~`) e commitar local.
- NÃO publicar, NÃO dar push, NÃO criar repositório remoto, NÃO criar conta em serviço nenhum, NÃO instalar dependência. Publicação é decisão do Lucas, depois.
- NÃO inventar dado: os dois exemplos abaixo são análises reais, já anonimizadas. Usar só os números que estão aqui. Não criar terceiro exemplo, depoimento, avaliação, selo, número de clientes nem "como visto em".
- NÃO incluir endereço, número de matrícula, cadastro municipal, nome ou CPF de ninguém.
- NÃO usar as palavras "parecer", "análise jurídica", "consultoria jurídica" nem "advogado" como descrição do serviço. O serviço é "triagem de documentos" / "leitura do anúncio e da matrícula".
- Se faltar informação: escolher a opção mais simples e reversível, seguir, e registrar a dúvida no RESUMO. Não parar para perguntar.

## Conteúdo da página (português do Brasil, texto direto, sem enfeite)
1. **Topo.** Nome provisório "Raio-X do Imóvel". Frase: cole o link do imóvel da Caixa e receba a lista de problemas do anúncio e da matrícula, com o custo estimado de cada um.
2. **O que o relatório traz** (lista curta): ocupação informada ou não; ônus na matrícula (penhora, hipoteca, indisponibilidade); como foi a intimação dos devedores; construção averbada ou não; quem paga IPTU e condomínio atrasados; data da certidão; conta final estimada (preço mínimo + ITBI, registro e débitos).
3. **Dois exemplos reais** (rotular cada um como "Exemplo real — endereço omitido"), em formato de relatório: veredito, ficha, tabela de problemas, o que não deu para verificar, conta final.

   **Exemplo 1 — Terreno de 630 m², capital da região Norte**
   - Veredito: tem problema contornável; não dá para chamar de limpo sem três checagens.
   - Avaliação da Caixa: R$ 310.000. Preço mínimo: R$ 179.821,49 (desconto de 41,99%). Venda online; recursos próprios ou financiamento, sem FGTS.
   - Problemas: (a) devedores não localizados, intimação por edital — gravidade média, risco de ação para anular a consolidação; (b) ocupação não informada no anúncio — média; (c) IPTU atrasado fica com o comprador se for menor que 10% da avaliação — até R$ 31.000 no pior caso; (d) certidão da matrícula vencida — baixa, custo de uma certidão nova; (e) a prefeitura avaliou o imóvel em R$ 86.450,28 para o ITBI da consolidação, muito abaixo da avaliação da Caixa — a conferir com preço de mercado; (f) endereço sem número e rua renomeada — baixa.
   - O que está bom: nenhuma penhora, hipoteca, indisponibilidade ou ação averbada; leilões negativos averbados segundo o anúncio.
   - Não deu para verificar pelos documentos: processos em nome dos ex-proprietários, estado real do lote, débito de IPTU, preço de mercado.
   - Conta (estimativa): ITBI, escritura e registro R$ 7 a 12 mil; IPTU de zero a R$ 31 mil; total provável R$ 187 a 223 mil, contra R$ 310 mil de avaliação.

   **Exemplo 2 — Casa, capital da região Norte**
   - Avaliação da Caixa: R$ 259 mil. Preço mínimo: R$ 146.284,32, só com recursos próprios.
   - O que está bom: intimação regular dos devedores; nenhum ônus de terceiros; leilões negativos averbados segundo o anúncio; a prefeitura avaliou em R$ 180.312,62 para o ITBI da consolidação e a última venda registrada foi de R$ 158.000 (2015) — o mínimo fica abaixo dos dois.
   - Problemas: ocupação e estado da casa não informados; IPTU atrasado pode ficar com o comprador (de zero a R$ 25,9 mil); só aceita pagamento à vista.
   - Conta (estimativa): ITBI, escritura e registro R$ 6 a 10 mil; total provável R$ 152 a 182 mil, contra R$ 259 mil de avaliação, fora desocupação e reforma.
   - Veredito: escrever "papel mais limpo que o exemplo 1; falta visitar o imóvel".
4. **Botão principal:** "Quero o raio-x do meu imóvel". Ao clicar, abre um formulário curto: link ou número do imóvel na Caixa + e-mail. Texto do formulário, honesto: "Estamos em fase de teste. Os primeiros pedidos recebem o relatório de graça por e-mail." Sem preço, sem campo de cartão, sem pagamento.
   - O destino do formulário fica numa constante no topo do script: `const DESTINO_FORMULARIO = "";`. Com ela vazia, o envio mostra "Em breve" e não manda nada a lugar nenhum. NÃO colocar e-mail do Lucas nem endpoint de terceiro.
   - Contar cliques no botão só em `localStorage` (dentro de try/catch). Sem analytics de terceiro.
5. **Rodapé com aviso, visível:** "Triagem de documentos públicos (anúncio e matrícula). Não é parecer jurídico nem recomendação de compra. Valores são estimativas. Antes de fazer proposta, visite o imóvel e consulte um advogado."

## Visual
Sóbrio, claro, com cara de documento: fundo branco ou quase branco, texto escuro, uma cor de destaque só, tabela legível no celular (a maioria vai abrir pelo telefone). Nada de fundo escuro, gradiente, cards arredondados em série, chips numerados ou paleta teal. Sem imagem de banco de fotos, sem logotipo da Caixa nem cores/identidade da Caixa — a página não pode parecer site oficial.

## Conferir antes de terminar
- Abre sem erro no console e funciona em largura de 375 px.
- Todos os números da página batem com este arquivo (conferir um a um).
- Nenhum endereço, matrícula, cadastro ou nome. Nenhuma das palavras proibidas.
- Nada fora de `~/Projetos/raio-x-imovel`.

## Retorno
Terminar com `## RESUMO` de no máximo 10 linhas: arquivos criados (caminho), o que ficou PENDENTE, dúvidas que resolveu sozinho. Saída de terminal com no máximo 40 linhas.
