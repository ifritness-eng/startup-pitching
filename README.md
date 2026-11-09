# startup-pitching

Набор для Claude Code: два субагента, **основатель** и **инвестор**, доводят идею стартапа до ума. Основатель строит материалы, инвестор их прожаривает, и так несколько раундов.

## Быстрый старт

```bash
git clone https://github.com/<you>/startup-pitching && cd startup-pitching && claude
```

Внутри Claude Code:

```
/refine Маркетплейс для аренды строительной техники в Казахстане
```

или по отдельности:

```
> попроси founder собрать деку для ideas/my-idea
> попроси investor провести mock-встречу по ideas/my-idea
> grill me: <идея>
```

Всё, что создают агенты, складывается в `ideas/<slug>/`: `facts.md`, `validation.md`, `narrative.md`, `deck.md`, `model.md`, `raise.md`, `review-N.md`, `responses.md`, `memo.md`.

## Агенты

| Агент | Роль | Скилы |
|---|---|---|
| `founder` | валидирует рынок, пишет нарратив, деку, финмодель, считает раунд и размытие, отвечает на возражения | startup-validator, fundraising-narrative, yc-pitch-deck, investor-materials, startup-financial-modeling, fundraising |
| `investor` | скептичный партнёр seed/A фонда: грубые вопросы, pre-mortem, red team, проверка цифр, вердикт и инвестмемо | asb-rude-qa, the-fool, grilling, investment-memo, startup-analysis |

## Скилы (`.claude/skills/`)

| Скил | Источник | Зачем |
|---|---|---|
| asb-rude-qa | asmartbear/asb-skills | грубые вопросы, «тест противоположности», честный вывод «идея плохая» |
| the-fool | jeffallan/claude-skills | 5 режимов критики: Сократ, red team, pre-mortem, аудит доказательств, диалектика |
| grilling | mattpocock/skills | допрос раундами с рекомендованными ответами |
| startup-validator | ailabs-393/ai-labs-claude-skills | ресёрч рынка, конкурентов, рисков |
| yc-pitch-deck | guia-matthieu/clawfu-skills | дека слайд за слайдом по YC/Sequoia |
| fundraising-narrative | guia-matthieu/clawfu-skills | инсайт и история до деки |
| investor-materials | affaan-m/ecc | согласованность цифр между всеми материалами |
| startup-financial-modeling | wshobson/agents | финмодель, сценарии, burn, runway, раунд |
| fundraising | refoundai/lenny-skills | процесс раунда, тайминг, советы из Lenny's Podcast |
| investment-memo | claude-office-skills/skills | инвестмемо от лица фонда |
| startup-analysis | himself65/finance-skills | разбор компании глазами VC |
| find-skills | vercel-labs/skills | поиск новых скилов |

Версии зафиксированы в `skills-lock.json`. Обновить: `npx skills update`.

Скилы взяты из сторонних репозиториев и работают с полными правами агента. Перед обновлением просматривайте изменения.
