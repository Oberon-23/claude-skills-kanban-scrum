# Skill do Claude para Scrum e Kanban

Uma skill para o [Claude](https://claude.ai) que ajuda a **organizar e entregar trabalho com Scrum e Kanban**: escolher o caminho certo, montar a estrutura e usar os dados do próprio trabalho para melhorar. Escrita em português do Brasil, para times de TI, atendimento, projetos e estudantes.

| Skill | Para que serve |
|---|---|
| [`scrum-kanban-gestao-trabalho`](skills/scrum-kanban-gestao-trabalho/SKILL.md) | Escolher entre Scrum, Kanban ou os dois juntos; montar Sprint, eventos, Definição de Pronto e Meta da Sprint; montar um quadro Kanban com limite de WIP, SLE e métricas de fluxo; diagnosticar quando o método não está funcionando. |

## O que muda na prática

Sem a skill, o Claude já sabe o que é uma Sprint ou um quadro Kanban. A skill acrescenta **fidelidade aos guias e disciplina**:

- **Separa o que o guia exige do que é sugestão.** Uma regra só é chamada de obrigatória se o Scrum Guide ou o Kanban Guide a exigem. O resto aparece como prática sugerida.
- **Respeita os limites oficiais do Scrum.** Os eventos seguem os limites de tempo do Scrum Guide, ajustados proporcionalmente quando a Sprint é curta, e a skill explica o ajuste.
- **Kanban de verdade, não só um quadro.** Pede o Definition of Workflow completo, limite de WIP explícito, SLE e as quatro métricas de fluxo (WIP, vazão, idade do item e tempo de ciclo).
- **Não inventa números.** Limite de WIP, SLE e percentis só com dados da equipe ou marcados como ponto de partida ilustrativo.
- **Scrum e Kanban juntos.** Mostra como cada evento do Scrum usa as práticas do Kanban, sem criar evento novo.
- **Diagnóstico.** Uma tabela de sintoma, causa provável e ação para Sprint que termina pela metade, quadro cheio sem andar, retrospectiva sem resultado e SLE sempre estourado.

## Como instalar

### No Claude (web, desktop ou celular)

1. Baixe o ZIP da pasta [`dist/`](dist/): [`scrum-kanban-gestao-trabalho.zip`](dist/scrum-kanban-gestao-trabalho.zip).
2. No Claude, abra **Customize > Skills**, clique em **+** e escolha **Upload a skill**.
3. Envie o ZIP e confira se a skill aparece ligada.

O uso de skills depende do plano e das configurações da sua conta. Se a opção não aparecer, veja a [central de ajuda do Claude](https://support.claude.com).

### No Claude Code

Copie a pasta de `skills/` para `~/.claude/skills/` (todas as suas sessões) ou para `.claude/skills/` dentro de um projeto:

```bash
git clone https://github.com/Oberon-23/claude-skills-kanban-scrum.git
cp -r claude-skills-kanban-scrum/skills/* ~/.claude/skills/
```

## Como usar

Não precisa chamar a skill pelo nome. Peça normalmente, e o Claude carrega a skill:

```text
Monta um quadro Kanban para o meu time de atendimento por chat, com limite de WIP e SLE.
```

```text
Quero adotar Scrum no meu time de 5 pessoas, com Sprint de 2 semanas.
Monta o calendário dos eventos, a Definição de Pronto e um modelo de Meta da Sprint.
```

```text
Nosso Scrum não está funcionando: a Sprint sempre termina com itens pela metade.
Me ajuda a entender o que está acontecendo.
```

Quanto mais contexto e dados você der (tamanho do time, tipo de trabalho, datas de início e fim dos itens), mais concreta fica a resposta. Sem dados, a skill entrega pontos de partida e diz o que coletar.

## Como foi testada

Cada teste rodou num **chat novo, sem citar o nome da skill**, para checar se ela dispara sozinha e se a resposta segue os guias.

| Teste | Resultado |
|---|---|
| Quadro Kanban para um time de atendimento por chat | Disparou sozinha; WIP por coluna, SLE por classe de serviço e premissas declaradas, com os números tratados como ponto de partida |
| Scrum para um time de 5 pessoas, Sprint de 2 semanas | Disparou sozinha; eventos dentro dos limites do Scrum Guide, Definição de Pronto e modelo de Meta da Sprint |

O histórico de ajustes está no [CHANGELOG](CHANGELOG.md).

## Skills complementares

A skill funciona sozinha. Ela também indica duas outras skills quando o pedido envolve mapear o fluxo antes de montar o quadro ou achar a causa de itens que ficam presos. Elas estão no repositório [claude-skills-processos-qualidade](https://github.com/Oberon-23/claude-skills-processos-qualidade):

- `mapeamento-automacao-processos`: SIPOC, BPMN, gargalos, desperdícios e automação.
- `ferramentas-qualidade-melhoria-continua`: PDCA, MASP, Pareto, Ishikawa, 5 Porquês, 5W2H e outras ferramentas da qualidade.

## Limites

- **Não substitui os guias oficiais.** É um resumo próprio: em dúvida sobre uma regra, confirme na versão vigente.
- **Escalonamento fora do escopo.** Vários times, frameworks de escala, certificações e ferramentas específicas (Jira, Azure DevOps) não são cobertos.
- **Resolve um time por vez.** Não acompanha uma carteira de times ou projetos ao longo do tempo.
- **A qualidade depende dos dados.** Sem datas reais dos itens, o SLE e as previsões são só pontos de partida.

## Referências

A skill é um resumo próprio, escrito com palavras próprias. Não reproduz trechos das obras abaixo, que são a fonte oficial e a leitura recomendada. Os autores e as organizações citados não têm relação com este projeto nem o endossam.

- Schwaber, K.; Sutherland, J. *The Scrum Guide* (2020), em [scrumguides.org](https://scrumguides.org/scrum-guide).
- Coleman, J. et al. *The Kanban Guide* (maio de 2025), em [kanbanguides.org](https://kanbanguides.org/the-kanban-guide/2025.5/).
- Scrum.org; Vacanti, D.; Yeret, Y. *The Kanban Guide for Scrum Teams* (2021), em [scrum.org](https://www.scrum.org/resources/kanban-guide-scrum-teams).

## Contribuir

Usou e algo saiu errado ou genérico? Abra uma [issue](https://github.com/Oberon-23/claude-skills-kanban-scrum/issues) com o pedido que você fez e o trecho da resposta. Ajustes entram só quando a falha se repete, para a skill não crescer demais.

## Autor

Breno · [GitHub](https://github.com/Oberon-23) · [LinkedIn](https://www.linkedin.com/in/brenosilvarangel)

Licença [MIT](LICENSE).
