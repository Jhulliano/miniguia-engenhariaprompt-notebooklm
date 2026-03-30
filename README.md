# Engenharia de Prompt na Prática com NotebookLM — Miniguia Completo 

## Contexto e Objetivos

### Sobre o Projeto

Este repositório documenta a construção de um **Caderno Temático no NotebookLM** com foco em **Engenharia de Prompt** — o processo iterativo de planejar, criar e otimizar as entradas (prompts) para orientar redes neurais a produzirem resultados previsíveis e de alta performance.

O tema foi escolhido por ser uma competência central para qualquer profissional que queira trabalhar com IA de forma produtiva. 

## Uso do NotebookLM

O NotebookLM foi utilizado como ferramenta central para este projeto, permitindo:

- Organização das fontes em um único ambiente
- Geração de respostas com base em múltiplos documentos (RAG)
- Iteração de prompts com contexto persistente
- Criação de sínteses estruturadas para estudo ativo

A abordagem adotada foi baseada em **aprendizado iterativo**, onde cada interação com a IA foi refinada progressivamente para melhorar a qualidade das respostas.

> O NotebookLM atuou não apenas como ferramenta de consulta, mas como um **ambiente de construção de conhecimento guiado por engenharia de prompt**.

[NotebookLM](https://notebooklm.google.com/notebook/c2ffa771-9615-4697-9239-555ec66dd38a/preview)

### Objetivos de Estudo

- Consolidar e aprofundar o entendimento sobre as principais técnicas de engenharia de prompt
- Construir um repertório reutilizável de prompts para diferentes cenários profissionais
- Explorar as capacidades do NotebookLM como ferramenta de síntese e estudo ativo

## Curadoria de Fontes

As fontes abaixo foram selecionadas por serem abertas, gratuitas e complementares entre si — combinando conteúdo em vídeo, artigos técnicos e documentação oficial. Todas foram carregadas no NotebookLM para compor o caderno temático.

| # | Título | Formato | Fonte | Link |
|---|--------|---------|-------|------|
| 1| Design de Prompt: Introdução a Engenharia de Prompt | 📹 Vídeo + Artigo | Curso em Vídeo | [cursoemvideo.com](https://www.cursoemvideo.com/blog/cursos-online-gratuitos/design-de-prompt-introducao-a-engenharia-de-prompt-para-interagir-com-inteligencias-artificiais/) |
| 2| What Is Prompt Engineering? 7 Techniques That Work in 2026 | 📄 Artigo | Medium (Jan Kisters) | [decodethefuture.org](https://decodethefuture.org/en/prompt-engineering/) |
| 3| Estudo Completo sobre Engenharia de Prompt | 📄 Artifact | Claude / Anthropic | [claude.ai/public/artifacts](https://claude.ai/public/artifacts/5d102200-831b-4a07-b0d9-6c20c1918c3c) |
| 4| O que é Engenharia de Prompt e quais as suas principais técnicas? | 📄 Artigo | Alura | [alura.com.br](https://www.alura.com.br/artigos/engenharia-prompt) |

> **Critério de curadoria:** priorizei fontes diversificadas em formato (vídeo + artigo + documentação), idioma (PT-BR e EN) e perspectiva — cobrindo desde introduções didáticas em português (Curso em Vídeo, Alura) até conteúdo técnico internacional atualizado para 2026 (Decode the future, Anthropic). Essa combinação garante tanto acessibilidade para iniciantes quanto profundidade para quem já tem base no tema.

---

## Engenharia de Prompts e "Cicatrizes"

Esta seção documenta o processo real de interação com o NotebookLM, incluindo os prompts testados, as respostas obtidas, as referências usadas pela IA e os ajustes necessários. Este é o coração metodológico do projeto.

---

### Rodada 1 — Mapeamento Inicial do Tema

**Objetivo:** Obter uma visão panorâmica das técnicas existentes.

**Prompt v1 (muito aberto):**
```
O que é engenharia de prompt?
```

**Resultado:** A Engenharia de prompt é a prática de criar, refinar e otimizar as instruções (os "prompts") que enviamos para modelos de inteligência artificial, como o ChatGPT, Gemini ou Claude. O objetivo fundamental é guiar a IA para que ela produza resultados mais precisos, relevantes e úteis para uma tarefa específica.

**Prompt v2 (melhorado com contexto e estrutura):**
```
Com base nas fontes carregadas, quais são as principais técnicas de engenharia de prompt
documentadas? Liste-as com nome, descrição de 2 linhas e um exemplo de uso prático.
```

**Resultado:** Com base nas fontes, as principais técnicas documentadas para otimizar a interação com IAs são:
- **Zero-shot Prompting:** Consiste em dar uma instrução direta sem fornecer exemplos prévios, confiando apenas no treinamento base do modelo. - `Exemplo:` "Classifique o sentimento desta crítica de filme como positiva, negativa ou neutra: 'Este filme é uma obra-prima'"
- **Few-shot Prompting:** Envolve fornecer alguns exemplos de entrada e saída (geralmente de 2 a 5) para que a IA aprenda o padrão e o formato desejado. - `Exemplo:` Fornecer três exemplos de descrições de produtos seguidas por seus respectivos códigos JSON antes de pedir a descrição de um novo item


**Aprendizado (cicatriz):** Prompts abertos geram respostas superficiais. Especificar o formato de saída desejado (lista, tabela, exemplos) melhora drasticamente a qualidade.

---

### Rodada 2 — Aprofundamento em Chain-of-Thought

**Objetivo:** Entender a técnica de raciocínio encadeado e quando usá-la.

**Prompt v1:**
```
Explique Chain-of-Thought.
```

**Resposta:** `Chain-of-Thought (CoT)` é uma técnica que instrui a IA a detalhar seu raciocínio lógico passo a passo antes de entregar a conclusão final. Em vez de pedir apenas o resultado bruto, você guia o modelo por etapas intermediárias, o que aumenta a precisão em problemas complexos de matemática ou lógica.

**Prompt v2 (com especificidade técnica):**
```
Explique a técnica Chain-of-Thought (CoT) prompting. Qual a diferença entre Zero-Shot CoT
e Few-Shot CoT? Em quais tipos de tarefas ela traz mais benefício e em quais pode ser
desnecessária ou prejudicial?
```

**Resultado:** A IA trouxe a distinção clara entre as duas variações, com exemplos de tarefas matemáticas e de raciocínio lógico, além de alertar que CoT pode gerar verbosidade excessiva em tarefas simples de classificação.

**Aprendizado (cicatriz):** Perguntas comparativas ("qual a diferença entre X e Y") e que incluem contra-exemplos ("quando NÃO usar") extraem respostas muito mais completas e úteis para o estudo.

---

### Rodada 3 — Comparação de Técnicas

**Objetivo:** Entender quando aplicar cada técnica.

**Prompt testado:**
```
Crie uma tabela comparativa entre as técnicas Zero-Shot, Few-Shot, Chain-of-Thought e
Role Prompting com as colunas: Técnica | Melhor caso de uso | Limitação principal |
Nível de complexidade do prompt.
```

**Resultado:** Excelente. A tabela gerada com as comparações ajuda a escolher a abordagem mais eficiente para cada desafio.

**Aprendizado (cicatriz):** Pedir explicitamente uma tabela com colunas definidas é uma das melhores formas de obter material estruturado e reutilizável do NotebookLM.

---

## Miniguia de Estudo — Entrega Final

---

### 1. Resumos Estruturados

#### O que é Engenharia de Prompt?

Engenharia de Prompt é o processo iterativo de planejar, criar e otimizar as entradas (prompts) para orientar redes neurais a produzirem resultados previsíveis e de alta performance. É uma habilidade multidisciplinar que combina lógica, linguística e conhecimento do domínio de aplicação.

Os LLMs funcionam como **motores de previsão**: não "entendem" o texto de forma humana, mas calculam distribuições probabilísticas para prever o próximo token com base no contexto. Dois conceitos técnicos são essenciais para isso:

- **Janela de Contexto:** memória de curto prazo do modelo durante uma interação. Em 2026, varia de 128 mil a mais de 2 milhões de tokens.
- **Mecanismo de Atenção:** o modelo atribui pesos diferentes a cada parte do texto. Informações no início e no fim do prompt tendem a receber maior atenção — fenômeno chamado de **"efeito de perda no meio"**.

---

#### Técnicas Principais

**Zero-Shot Prompting**
Consiste em pedir ao modelo que execute uma tarefa sem fornecer exemplos prévios. Funciona bem em modelos grandes e treinados com RLHF. É o ponto de partida para qualquer interação.

```
Classifique o sentimento do texto abaixo como positivo, negativo ou neutro:
"O produto chegou no prazo e superou minhas expectativas."
```

---

**Few-Shot Prompting**
Fornece alguns exemplos (shots) antes da instrução principal. Guia o modelo a seguir um padrão específico de resposta, especialmente útil para formatos personalizados.

```
Classifique o sentimento:
Texto: "Detestei o atendimento." → Negativo
Texto: "Produto razoável." → Neutro
Texto: "Experiência incrível!" → Positivo
Texto: "Demorou mais do que o esperado, mas chegou." → ???
```

---

**Chain-of-Thought (CoT)**
Incentiva o modelo a "pensar em voz alta", decompondo o raciocínio em etapas intermediárias. Aumenta significativamente a acurácia em problemas matemáticos, lógicos e de múltiplos passos.

```
Resolva passo a passo: Se um produto custa R$120 com 15% de desconto, qual o valor final?
Mostre cada etapa do cálculo antes de dar a resposta.
```

---

**Zero-Shot CoT**
Variação simplificada do CoT que usa apenas a instrução "Vamos pensar passo a passo" ao final do prompt, sem exemplos adicionais.

```
Um trem parte às 08h e chega às 14h30, com uma parada de 45 minutos. Qual a duração
total da viagem em movimento? Vamos pensar passo a passo.
```

---

**Role Prompting**
Atribui um papel ou persona ao modelo para contextualizar o tom, o nível de expertise e o foco das respostas.

```
Você é um engenheiro sênior de software com 15 anos de experiência em Python.
Revise o código abaixo e aponte os 3 principais problemas de performance:
[código]
```

---

**Prompt com Restrições**
Define explicitamente o que o modelo deve e não deve fazer, o formato de saída e o escopo da resposta.

```
Resuma o texto abaixo em até 5 bullet points, usando linguagem técnica.
Não inclua opiniões. Foque apenas em dados e fatos objetivos.
[texto]
```

---

**Iterative Refinement**
Estratégia de refinamento progressivo: começa com um prompt simples e vai adicionando camadas de especificidade baseadas nas respostas anteriores.

```
1ª iteração: "Explique machine learning."
2ª iteração: "Agora foque apenas em aprendizado supervisionado."
3ª iteração: "Dê 3 exemplos práticos de uso em e-commerce."
```

---

**Self-Consistency**
Gera múltiplas cadeias de raciocínio independentes para a mesma pergunta e seleciona a resposta majoritária. Reduz a variância e aumenta a confiabilidade em tarefas de senso comum e aritmética.

```
Resolva o problema abaixo de três formas diferentes e independentes.
Ao final, indique qual resposta apareceu mais vezes e por quê ela é a mais confiável.

Problema: [PROBLEMA]
```

---

**Least-to-Most Prompting**
Decompõe um problema complexo em subproblemas menores, resolvendo-os em sequência. Útil quando a tarefa exige múltiplas etapas interdependentes.

```
Para resolver [TAREFA COMPLEXA], vamos dividir em partes:
1. Primeiro, identifique os subproblemas que compõem a tarefa.
2. Liste-os em ordem de dependência (do mais simples ao mais complexo).
3. Resolva cada subproblema sequencialmente antes de avançar.
```

---

**Meta-Prompting**
Solicita que o próprio modelo crie ou otimize um prompt para uma tarefa específica. Aumenta a eficiência de tokens e reduz vieses introduzidos por exemplos estáticos.

```
Você é um especialista em engenharia de prompt. Crie o prompt ideal para que
um LLM execute a seguinte tarefa com máxima precisão: [DESCRIÇÃO DA TAREFA].
O prompt deve incluir persona, formato de saída e restrições relevantes.
```

---

| Técnica | Melhor caso de uso | Limitação principal | Complexidade |
|---|---|---|---|
| Zero-Shot | Tarefas simples, traduções e classificações básicas | Pode falhar em tarefas específicas de domínio | Baixa |
| Few-Shot | Padronização de formato e tom; aumento de precisão | Ocupa espaço de contexto | Média |
| Chain-of-Thought | Problemas lógicos, matemáticos e análises complexas | Pode gerar verbosidade desnecessária | Média-Alta |
| Self-Consistency | Redução de variância em tarefas de senso comum e aritmética | Consome mais tokens (múltiplas gerações) | Alta |
| Role Prompting | Ajuste de tom, profundidade e vocabulário técnico | Persona pode ser inconsistente em prompts longos | Baixa-Média |
| Least-to-Most | Tarefas que exigem múltiplas etapas sequenciais | Requer mapeamento prévio do problema | Alta |
| Meta-Prompting | Eficiência de tokens e redução de vieses | Exige validação humana do prompt gerado | Alta |
| Restrições explícitas | Outputs estruturados e controlados | Requer conhecimento do domínio para definir bem | Média |

---

---

#### Engenharia de Contexto e Tecnologias Avançadas

**RAG (Retrieval-Augmented Generation)**
Técnica que combina o poder dos LLMs com bases de conhecimento externas. O sistema busca informações relevantes em documentos antes de gerar a resposta, reduzindo alucinações e garantindo dados atualizados. É a base do funcionamento do próprio NotebookLM.

**Formatação com Tags XML e Markdown**
O uso de tags estruturais como `<instrucoes>`, `<exemplo>` e `<contexto>` é altamente eficaz — especialmente para modelos da família Claude (Anthropic) — pois evita que o modelo se perca em documentos longos. Markdown com títulos (`#`), negrito e listas também auxilia na interpretação da hierarquia da informação.

---

#### Segurança, Ética e Conformidade

**Prevenção de Alucinações**
- Instruir explicitamente: *"Se você não souber a resposta, diga que não sabe"*
- Ajustar a **temperatura** para valores baixos (0.1–0.3) em tarefas factuais
- Exigir que o modelo cite trechos do texto fornecido como evidência

**Segurança de Prompt (Prompt Injection)**
Ataques onde o usuário tenta burlar as diretrizes do sistema com instruções como *"Ignore as instruções anteriores"*. As defesas incluem: separação clara entre mensagens de sistema e de usuário, filtragem de entrada/saída e uso de "canários de prompt".


---

### 2. Glossário

| Termo | Definição |
|---|---|
| **LLM (Large Language Model)** | Modelo de linguagem de grande escala treinado em vastos conjuntos de dados textuais para gerar e compreender linguagem natural. Ex.: GPT-4, Claude, Gemini. |
| **Prompt** | Instrução, pergunta ou contexto fornecido a um modelo de linguagem para guiar sua resposta. |
| **Token** | Unidade básica de processamento de texto em LLMs. Pode ser uma palavra, parte de uma palavra ou um caractere. Afeta custo e limites de contexto. |
| **Contexto (Context Window)** | Quantidade máxima de tokens que um modelo consegue processar em uma interação. Em 2026, varia de 128 mil a mais de 2 milhões de tokens. |
| **Mecanismo de Atenção** | Arquitetura que atribui pesos diferentes a cada parte do prompt. Causa o "efeito de perda no meio", onde informações centrais recebem menos atenção. |
| **Zero-Shot** | Técnica em que o modelo executa uma tarefa sem exemplos prévios no prompt. |
| **Few-Shot** | Técnica que inclui de 2 a 5 exemplos no prompt para guiar o padrão de resposta esperado. |
| **Chain-of-Thought (CoT)** | Técnica que incentiva o modelo a externalizar seu raciocínio em etapas, melhorando a acurácia em tarefas complexas. |
| **Self-Consistency** | Variação do CoT que gera múltiplas cadeias de raciocínio e seleciona a resposta majoritária para aumentar confiabilidade. |
| **Least-to-Most** | Técnica que decompõe um problema complexo em subproblemas menores resolvidos sequencialmente. |
| **Meta-Prompting** | Técnica em que o modelo é instruído a criar ou otimizar o próprio prompt para uma tarefa. |
| **Role Prompting** | Atribuição de uma persona ou papel ao modelo para condicionar tom, expertise e foco das respostas. |
| **RAG (Retrieval-Augmented Generation)** | Técnica que permite à IA consultar fontes externas (como os documentos deste caderno) antes de responder, garantindo que o conhecimento seja factual e ancorado (grounded), minimizando alucinações. |
| **Prompt Injection** | Ataque em que instruções maliciosas tentam sobrescrever as diretrizes do sistema (ex: "Ignore as instruções anteriores"). |
| **Grounding** | Técnica de ancorar as respostas do modelo a fontes ou fatos específicos, reduzindo alucinações. |
| **Alucinação** | Fenômeno em que o modelo gera informações falsas ou inventadas com aparente confiança. |
| **Deriva de Prompt (Prompt Drift)** | Degradação gradual da performance de um prompt em produção à medida que os modelos e entradas evoluem. |
| **RLHF** | Reinforcement Learning from Human Feedback — técnica de treinamento que usa feedback humano para alinhar o comportamento do modelo. |
| **System Prompt** | Instrução de nível superior fornecida antes da conversa para definir o comportamento geral e persistente do modelo. |
| **Temperatura** | Parâmetro que controla a criatividade/aleatoriedade das respostas. Valores baixos (0.1–0.3) = mais preciso; valores altos = mais criativo. |
| **Iterative Refinement** | Estratégia de melhoria progressiva de prompts baseada nas respostas obtidas em rodadas anteriores. |
| **Template de Prompt** | Estrutura reutilizável de prompt com placeholders substituíveis como `[TEMA]`, `[CONTEXTO]` e `[OBJETIVO]`. |

---

### 3. Prompts Reutilizáveis

#### Resumo de Documento Técnico
```
Você é um especialista em [ÁREA]. Leia o documento abaixo e produza:
1. Um resumo executivo de até 3 parágrafos
2. Os 5 pontos mais importantes em bullet points
3. Uma frase que capture a ideia central do documento

Responda apenas com base no conteúdo fornecido. Não adicione inferências externas.

[DOCUMENTO]
```

---

#### Explicação para Iniciantes
```
Explique o conceito de [TEMA] para alguém que nunca teve contato com [ÁREA].
Use linguagem simples, evite jargões técnicos e inclua uma analogia do cotidiano.
Limite a resposta a 3 parágrafos.
```

---

#### Análise Crítica de Texto
```
Analise criticamente o texto abaixo considerando:
1. Argumentos centrais apresentados
2. Pontos fortes da argumentação
3. Possíveis lacunas ou fraquezas lógicas
4. Contexto que pode estar ausente

Seja objetivo e equilibrado. Não emita julgamentos de valor.

[TEXTO]
```

---

#### Geração de Código Comentado
```
Você é um desenvolvedor sênior de [LINGUAGEM]. Escreva um código para [OBJETIVO].
Requisitos:
- Comente cada bloco lógico explicando o raciocínio
- Siga as boas práticas de [LINGUAGEM]
- Inclua tratamento de erros básico
- Adicione um exemplo de uso no final

[CONTEXTO ADICIONAL SE NECESSÁRIO]
```

---

#### Resolução de Problema Passo a Passo
```
Resolva o problema abaixo usando raciocínio encadeado (passo a passo):
1. Identifique e restate o problema com suas próprias palavras
2. Liste as informações disponíveis
3. Resolva cada etapa explicitamente, mostrando o raciocínio
4. Apresente a solução final com justificativa

Problema: [DESCRIÇÃO DO PROBLEMA]
```

---

#### Comparação Estruturada
```
Compare [OPÇÃO A] e [OPÇÃO B] para o contexto de [CENÁRIO DE USO].
Formato de resposta:
| Critério | [OPÇÃO A] | [OPÇÃO B] |
Use os critérios: facilidade de uso, custo, escalabilidade, limitações e melhor caso de uso.
Conclua com uma recomendação objetiva baseada nos critérios.
```

---

## Conclusões e Próximos Passos

Este projeto demonstrou que o **NotebookLM** transcende a função de um simples leitor de PDFs, consolidando-se como um ambiente de **estudo ativo e síntese inteligente**. Através da curadoria técnica e da aplicação estratégica de Engenharia de Prompt, foi possível transformar dados brutos em um guia estruturado e prático.

**Principais aprendizados do processo:**

- **Domínio do Contexto:** A qualidade da resposta está diretamente ligada à clareza das restrições e ao papel (persona) atribuído à IA.
- **RAG na Prática:** O uso do NotebookLM provou que o ancoramento (*grounding*) em fontes confiáveis é a defesa mais eficaz contra alucinações.
- **Estrutura é Conteúdo:** Especificar o formato de saída (como tabelas e bullet points) não apenas organiza a resposta, mas força a IA a processar a informação de forma mais analítica.
- **Iteração Progressiva:** O conceito de "cicatrizes" mostrou que o primeiro prompt raramente é o final; o refinamento contínuo é o que separa resultados genéricos de resultados profissionais.

**Próximos passos:**

- [ ] **Aprofundamento Técnico:** Testar as técnicas de *Self-Consistency* e *Least-to-Most* em conjuntos de dados mais complexos.
- [ ] **Automação de Prompts:** Utilizar *Meta-Prompting* para criar templates personalizados para diferentes fluxos de trabalho (ex: revisão de código vs. análise de texto).
- [ ] **Segurança e Ética:** Estudar técnicas avançadas de defesa contra *Prompt Injection* em aplicações que utilizam LLMs em produção.
- [ ] **Benchmarking:** Comparar como o mesmo conjunto de fontes curadas é interpretado por diferentes modelos (Gemini 1.5 Pro vs. GPT-4o) dentro e fora de arquiteturas RAG.
---

## 🔗 Recursos Adicionais

- [Awesome Prompt Engineering (GitHub)](https://github.com/promptslab/Awesome-Prompt-Engineering)
- [Prompt Engineering Interactive Tutorial — Anthropic](https://github.com/anthropics/prompt-eng-interactive-tutorial)
- [ChatGPT Prompt Engineering for Developers — DeepLearning.AI](https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/)

---

*Projeto desenvolvido para o desafio prático da [DIO](https://www.dio.me/) — Explorando IA como ferramenta de aprendizagem ativa com NotebookLM.*
