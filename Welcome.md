
You are a Senior Developer with 15 years of experience

lazagne
gen-lang-client-0803597625
setx GEMINI_API_KEY AIzaSyD1PqbDxTvsOEyzT7rXExTMg-72Qw3SS_k


Listed directory history
Listed directory landscape
Viewed 577-9705.json:1-208
Viewed 655-15736-metadata-response.json:1-5
Viewed 611-9584.json:1-269
Viewed 799-24929-design-context-response.json:1-3
Listed directory FigmaExtractor
Listed directory Documentation
Viewed MasterPrompt.md:1-90
Viewed mcp_config.json:1-17
Viewed 655-15736.json:1-8
Searched for "landscape"

В папке `Documentation\history` (включая подпапку `landscape`) ответы от Figma MCP представлены в разных форматах по нескольким причинам:

### 1. Использование разных инструментов (Tools)
Формат зависит от того, какой инструмент MCP использовался для получения данных:
*   **`get_design_context`**: Возвращает AI-сгенерированный код (часто React + Tailwind) и стили (например, `655-15736.json` или `landscape\611-9584.json`).
*   **`get_node_metadata`**: Возвращает сырую иерархию узлов в формате XML (например, файлы с суффиксом `-metadata-response.json`).

### 2. Изменение логики сохранения (Caching)
В истории проекта видны следы разных подходов к кэшированию:
*   **Raw Code (`577-9705.json`, `landscape\611-9584.json`)**: В этих файлах сохранено только тело JavaScript/React кода, извлеченное из ответа MCP, но с расширением `.json`.
*   **Full JSON Object (`655-15736.json`)**: Файл содержит объект с полями `nodeId`, `fileKey` и вложенным объектом `designContext`, в котором уже находится код и стили.
*   **Raw MCP Response (`799-24929-design-context-response.json`)**: Полный необработанный ответ от инструмента, где иерархия представлена в виде XML в поле `output`.

### 3. Параметры генерации
Инструмент `get_design_context` может принимать параметр `framework` (например, `react`, `xml`, `compose`). В зависимости от этого параметра один и тот же инструмент может вернуть либо готовый код, либо XML-структуру макета.

### Почему это важно для проекта:
Согласно `MasterPrompt.md` (пункт 9), `node-id` является единственным источником структуры. Разница в форматах возникла из-за эволюции методов сбора данных или использования разных инструментов для разных задач (например, `metadata` для анализа структуры, а `design_context` для быстрой конвертации в код).

**Итог:** Различия обусловлены тем, что в истории накоплены результаты работы разных версий агентов и разных инструментов Figma MCP (одни возвращают код, другие — XML-метаданные).