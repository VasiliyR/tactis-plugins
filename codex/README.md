# Tactis Ads для Codex

Начни с полезной задачи для бизнеса в чате своего ИИ-агента. Выбери приоритеты роста, подготовь предложение и объявления, проверь страницу или разберись в результатах маркетинга.

Сравни кампании и периоды, разбери поисковые фразы, расходы и конверсии вместе с данными Метрики. Получи понятные графики и таблицы, подготовь ключевые и минус-фразы, объявления и план работы. Поддерживаемые изменения выполняются в пределах согласованного поручения; затем можно оценить результат.

Tactis сохраняет контекст клиента, решения и историю работы. Продолжай в новом чате с уже известной ситуацией. Отчёт для клиента можно подготовить по запросу.

Через то же подключение подготовь варианты рекламного текста, первую правку страницы или SEO-задание. Сравни экономику услуг при наличии данных о продажах и затратах, составь предложение для повторной покупки и выбери приоритеты месяца. Сохрани конкретный материал и вернись к его проверке в следующем чате. Доступные действия зависят от подключённых источников; готовый текст или план сам по себе не меняет сайт и не отправляет сообщения клиентам.

Создай бизнес в Tactis и выбери задачу. Для предложения, текстов и плана можно начать со своих материалов; для анализа подключи нужные данные. Задачи, источники и сохранённые результаты доступны в кабинете, а работа с агентом продолжается в твоём чате.

## Попробуй в чате

- Разбери мою рекламу за последние 30 дней и выбери три главных действия.
- Что умеет Tactis? Помоги выбрать полезную первую задачу для моего бизнеса.
- Продолжи работу по клиенту: покажи прошлые решения и следующий шаг.

Сайт: https://tactis.ru

## Установка

Добавь GitHub marketplace штатным менеджером своей программы:

```text
codex plugin marketplace add https://github.com/VasiliyR/tactis-plugins.git --ref main
codex plugin add tactis@tactis-ads
```

Для Codex сохрани включённый плагин с навыками и зарегистрируй тот же `tactis_ads` как штатный Config MCP server, чтобы агенту были доступны все инструменты. В записи `tactis` из `codex plugin list --json` при `source.source="local"` получи фактический корень из `source.path`; это путь установленного payload. Прочитай корневые `release.json`, `.mcp.json` и `.codex-plugin/plugin.json`. Через marketplace list проверь официальный Git source/ref. Manifest version, `host=codex`, package version/digest и hashes файлов сверь с опубликованным Codex package; формат hashes — `sha256-normalized-payload-map.1`, а не raw hash MCP JSON. Подробная нормализация и проверки описаны в `skills/tactis/references/plugin-updates.md`.

Проверь `codex mcp --help`, `codex mcp add --help`, `codex mcp list --json` и `codex mcp get tactis_ads --json`. Если Config записи нет, используй `codex mcp add tactis_ads --url <URL из установленного .mcp.json>`. При существующей записи сравни URL и известные requested OAuth scopes; чужой URL или другие scopes — конкретный конфликт, без перезаписи и нового alias. Неизвестные scopes оставь непроверенными.

Из фактически установленного `.mcp.json`, `mcpServers.tactis_ads.headers`, перенеси только шесть публичных headers в документированный Codex config `mcp_servers.tactis_ads.http_headers` того же scope: `X-Tactis-Methodology-Version`, `X-Tactis-Adapter-Version`, `X-Tactis-Common-Digest`, `X-Tactis-Package-Host`, `X-Tactis-Package-Version`, `X-Tactis-Package-Digest`. В родительской таблице `[mcp_servers.tactis_ads]`, вне `http_headers`, задай числом `tool_input_schema_max_bytes = 16384` для полной входной схемы Work. Это настройка только этого Config server, не изменение лимитов bundled plugin. Сверь значения с marker; сохрани все остальные настройки и headers, OAuth credentials, auth-параметры, scopes, approval policy и tool permissions. Не копируй Authorization/Cookie, не редактируй cache/credential files и не используй headersHelper. Прочитай config обратно, не выводя секреты. Если host не поддерживает server schema key, обозначь несовместимость без обещания полной схемы. Config MCP с тем же ключом имеет приоритет над bundled MCP, а плагин продолжает поставлять навыки.

Для native RankedSearch проверь `codex features list`: ключ `code_mode_tool_search` должен распознаваться, а модель/host — поддерживать native tool search. При поддержке включи `features.code_mode_tool_search=true` в текущем профиле или сессии. Настройка действует на все MCP профиля; сохрани остальные features, auth, policy и config. Это не API `defer_loading` и не allowlist `enabled_tools`/`disabled_tools`. Без поддержки сохрани полный доступ и вход через сценарии плагина без обещания ranked search.

Native add может сразу начать обычный OAuth. Если вход ещё требуется, настрой headers и server schema key до финального `codex mcp login tactis_ads` и заверши штатный вход в браузере. Рабочий OAuth сохраняй, не выполняй logout/login без причины. После каждого обновления плагина заново прочитай native `source.path`, проверь новую копию и синхронизируй эти headers в том же Config MCP, сохранив `tool_input_schema_max_bytes = 16384`, до итогового `get_plugin_update_status`. Затем открой новый чат или перезапусти приложение и проверь реальные callable tools, навыки, чтение проекта и поля `continuation`, `learning`, `signal_responses` в фактической сигнатуре Work. Полный canonical contract при необходимости читает существующий `get_tool_contract`. При RankedSearch обычное поручение должно находить инструмент через native `tools.tool_search`, затем читать декларацию и вызывать canonical tool с обычным approval. Отказ host permissions/approval остаётся ограничением; их не ослабляют для установки.

Источник: ветка `main`, канал совместимости `v1`; плагин `tactis@tactis-ads`. Сверь команды с `--help` своей версии. Подробные шаги: https://tactis.ru/install.md?agent_host=codex.

Авторизация MCP выполняется отдельно в браузере: Codex Authenticate, Claude Code `/mcp`, ZCode Settings → MCP → Open authorization. Выбери проект и подтверди показанные права. Плагин содержит общие навыки и настройки, без личных credentials.

Обновляй только существующий Tactis штатным менеджером, сохраняя OAuth и остальные плагины. Затем обнови контекст или открой новый чат: проверь навыки из `methodology.json.skills`, `get_plugin_update_status`, `list_projects` и `get_project_brief`. Замена исходников сама по себе не подтверждает обновление установленной копии или уже открытого чата.

Claude Desktop, claude.ai и Cowork пока не входят в поддержанные OAuth-профили. Изменения выполняются в пределах согласованного поручения; доступ отзывается в кабинете.
