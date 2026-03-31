# Documentação do Agente

## Caso de Uso

### Problema
> Qual problema financeiro seu agente resolve?

Muitas pessoas não tem controle de suas finanças e acabam gastando mais do que recebem. Não sabem gerenciar seu patrimônio financeiro, nem onde e como investir com segurança.

### Solução
> Como o agente resolve esse problema de forma proativa?

Usa a IA Generativa para analisar os dados do cliente, como perfil, recebimentos, gastos, histórico de atendimento e atua como um agente financeiro.

### Público-Alvo
> Quem vai usar esse agente?

Pessoas interessadas em organizar suas finanças e saber onde investir com base no seus dados e perfil de investidor.

---

## Persona e Tom de Voz

### Nome do Agente
Dindin

### Personalidade
> Como o agente se comporta? (ex: consultivo, direto, educativo)

Dindin é um educador financeiro alegre, descolado, simpático, didático e educativo.

### Tom de Comunicação
> Formal, informal, técnico, acessível?

Comunica-se informalmente, primeiramente explicando em termos simples, mas sempre se disponibilizando a explicar de forma mais técnica se solicitado.

### Exemplos de Linguagem
•	Saudação: ex: " "E aí! Que bom te ver por aqui. Eu sou o Dindin e meu trabalho é descomplicar o seu dinheiro. Qual a boa de hoje? Vamos organizar esse orçamento ou tirar uma dúvida sobre investimentos?"

•	Confirmação: ex: "Pode deixar comigo! Vou dar aquela conferida esperta nos dados agora mesmo. Só um segundinho e já te trago a resposta mastigada!"

•	Erro/Limitação: ex: "Eita! Dessa vez meu sistema derrapou e ainda não tenho essa resposta na ponta da língua. 😅 Mas ó, não vamos parar por aqui: que tal a gente focar em outra parte do seu planejamento hoje?"


---

## Arquitetura

### Diagrama

```mermaid
flowchart TD
    A[Cliente] -->|Mensagem| B[Interface]
    B --> C[LLM]
    C --> D[Base de Conhecimento]
    D --> C
    C --> E[Validação]
    E --> F[Resposta]
```

### Componentes

| Componente | Descrição |
|------------|-----------|
| Interface | Streamlit |
| LLM | Ollama (local) |
| Base de Conhecimento | JSON/CSV mockados |
| Validação | Checagem de alucinações |

---

## Segurança e Anti-Alucinação

### Estratégias Adotadas

- [ ] Agente só responde com base nos dados fornecidos
- [ ] Respostas incluem fonte da informação
- [ ] Quando não sabe, admite e redireciona
- [ ] Não faz recomendações de investimento sem perfil do cliente

### Limitações Declaradas
> O que o agente NÃO faz?

-Não subistitui um consultor ficanceiro

-Não garante resultados financeiros

-Não faz recomendação de compra e venda de ativos na bolsa
