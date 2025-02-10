# LangChain介紹持續累績中]
參考網址:(https://python.langchain.com/docs/introduction/)

**LangChain**是一個由大型語言模型 (LLM) 驅動的應用程式開發框架。

LangChain 簡化了 LLM 應用程式生命週期的每個階段：

- **開發**：使用 LangChain 的開源[元件](https://python.langchain.com/docs/concepts/)和[第三方整合](https://python.langchain.com/docs/integrations/providers/)來建立您的應用程式。使用[LangGraph](https://python.langchain.com/docs/concepts/architecture/#langgraph)建立具有一流串流媒體和人機互動支援的狀態代理。
- **生產化**：使用[LangSmith](https://docs.smith.langchain.com/)檢查、監控和評估您的應用程序，以便您可以不斷優化和自信地部署。
- **部署：使用**[LangGraph 平台](https://langchain-ai.github.io/langgraph/cloud/)將您的 LangGraph 應用程式轉變為可用於生產的 API 和助手。

![此圖概述了 LangChain 框架的層次組織，顯示了跨多個層級的互連部分。](https://python.langchain.com/svg/langchain_stack_112024_dark.svg "LangChain 框架概述")

LangChain 實現了大型語言模型和相關技術（如嵌入模型和向量儲存）的標準接口，並與數百家提供者整合。請參閱[整合](https://python.langchain.com/docs/integrations/providers/)頁面以了解更多資訊。

選擇[聊天模型](https://python.langchain.com/docs/integrations/chat/)：

格羅克▾

```
pip install -qU "langchain[groq]"
```

```
import getpassimport osif not os.environ.get("GROQ_API_KEY"):  os.environ["GROQ_API_KEY"] = getpass.getpass("Enter API key for Groq: ")from langchain.chat_models import init_chat_modelmodel = init_chat_model("llama3-8b-8192", model_provider="groq")
```

```
model.invoke("Hello, world!")
```

筆記

這些文件重點介紹 Python LangChain 庫。[點擊此處](https://js.langchain.com/)獲取有關 JavaScript LangChain 庫的文檔。

## [大樓](https://python.langchain.com/docs/introduction/#architecture "Direct link to Architecture")

LangChain框架由多個開源程式庫組成。請參閱[架構](https://python.langchain.com/docs/concepts/architecture/)頁面以了解更多資訊 。

- **`langchain-core`**：聊天模型和其他元件的基本抽象。
- **整合包**（例如`langchain-openai`，`langchain-anthropic`等）：重要的整合已拆分為輕量級包，由 LangChain 團隊和整合開發人員共同維護。
- **`langchain`**：構成應用程式認知架構的鏈、代理和檢索策略。
- **`langchain-community`**：社區維護的第三方整合。
- **`langgraph`**：用於將 LangChain 組件組合成具有持久性、串流和其他關鍵功能的生產就緒應用程式的編排框架。參見[LangGraph 文檔](https://langchain-ai.github.io/langgraph/)。

## [指南](https://python.langchain.com/docs/introduction/#guides "Direct link to Guides")

### [教學](https://python.langchain.com/docs/introduction/#tutorials "Direct link to tutorials")

如果您希望建立某些特定的東西，或者您更傾向於動手學習，請查看我們的[教程部分](https://python.langchain.com/docs/tutorials/)。這是最好的起點。

這些是最好的入門方法：

- [建立一個簡單的LLM應用程式](https://python.langchain.com/docs/tutorials/llm_chain/)
- [建構聊天機器人](https://python.langchain.com/docs/tutorials/chatbot/)
- [建立代理](https://python.langchain.com/docs/tutorials/agents/)
- [LangGraph簡介](https://langchain-ai.github.io/langgraph/tutorials/introduction/)

[在此處](https://python.langchain.com/docs/tutorials/)探索 LangChain 教程的完整列表，並在此處查看其他[LangGraph 教程](https://langchain-ai.github.io/langgraph/tutorials/)。要了解有關 LangGraph 的更多信息，請查看我們的第一門 LangChain Academy 課程*《LangGraph 簡介》*，可[在此處](https://academy.langchain.com/courses/intro-to-langgraph)獲取。

### [操作](https://python.langchain.com/docs/how_to/)[指南](https://python.langchain.com/docs/introduction/#how-to-guides "直接連結到操作指南")

[您會在這裡](https://python.langchain.com/docs/how_to/)找到"我該如何......？"的簡短答案。問題類型。這些操作指南並未深入涵蓋主題 -- 您可以在[教學課程](https://python.langchain.com/docs/tutorials/)和[API 參考](https://python.langchain.com/api_reference/)中找到相關資料。但是，這些指南將幫助您使用[聊天模型](https://python.langchain.com/docs/how_to/#chat-models)、 [向量儲存](https://python.langchain.com/docs/how_to/#vector-stores)和其他常見的 LangChain 元件快速完成常見任務。

在此查看[LangGraph 的具體操作方法](https://langchain-ai.github.io/langgraph/how-tos/)。

### [概念](https://python.langchain.com/docs/concepts/)[指南](https://python.langchain.com/docs/introduction/#conceptual-guide "直接連結至概念指南")

介紹您需要了解的 LangChain 的所有關鍵部分！[在這裡](https://python.langchain.com/docs/concepts/)您可以找到所有 LangChain 概念的高級解釋。

若要深入了解 LangGraph 概念，請查看[此頁面](https://langchain-ai.github.io/langgraph/concepts/)。

### [整合](https://python.langchain.com/docs/introduction/#integrations "Direct link to integrations")

LangChain 是豐富的工俱生態系統的一部分，它與我們的框架整合並在其基礎上進行構建。如果您希望快速啟動並運行[聊天模型](https://python.langchain.com/docs/integrations/chat/)、[向量儲存](https://python.langchain.com/docs/integrations/vectorstores/)或特定提供者的其他 LangChain 元件，請查看我們不斷增長的整合[清單](https://python.langchain.com/docs/integrations/providers/)。

### [API](https://python.langchain.com/api_reference/)[參考](https://python.langchain.com/docs/introduction/#api-reference "直接連結到 api-reference")

前往參考部分以取得 LangChain Python 套件中所有類別和方法的完整文件。

## [生態系統](https://python.langchain.com/docs/introduction/#ecosystem "Direct link to Ecosystem")

### [🦜🛠️ ](https://docs.smith.langchain.com/)[LangSmith](https://python.langchain.com/docs/introduction/#%EF%B8%8F-langsmith "直接連結到️-langsmith")

追蹤和評估您的語言模型應用程式和智慧代理，以幫助您從原型轉向生產。

### [🦜🕸️ ](https://langchain-ai.github.io/langgraph)[LangGraph](https://python.langchain.com/docs/introduction/#%EF%B8%8F-langgraph "直接連結至️-langgraph")

使用 LLM 建立有狀態、多參與者的應用程式。與 LangChain 順利集成，但單獨使用也可以。 LangGraph 為生產級代理商提供支持，受到 Linkedin、Uber、Klarna、GitLab 等的信賴。

## 其他[資源](https://python.langchain.com/docs/introduction/#additional-resources "直接連結到其他資源")

### [版本](https://python.langchain.com/docs/introduction/#versions "Direct link to versions")

查看 v0.3 中的變化，了解如何遷移遺留程式碼，閱讀我們的版本控制策略等。

### [安全](https://python.langchain.com/docs/introduction/#security "Direct link to security")

閱讀[安全](https://python.langchain.com/docs/security/)最佳實踐，以確保您使用 LangChain 進行安全開發。

### [貢獻](https://python.langchain.com/docs/introduction/#contributing "Direct link to contributing")

查看開發人員指南，以取得有關貢獻的指導並協助您設定開發環境。


好的，身為一個資訊人員，我來為您詳細介紹一下 LangChain 這個強大的框架：

**LangChain 的目的**

LangChain 的主要目標是簡化**大型語言模型 (LLM) 應用程式的開發流程**。它提供了一個全面的框架，讓開發者可以更輕鬆地**建構、生產化和部署**由 LLM 驅動的智慧應用程式。簡單來說，它就是一個工具箱，裡面裝滿了各種好用的工具和組件，讓您不用從頭開始，就能快速打造出基於 LLM 的應用。

**LangChain 的主要功能**

LangChain 提供了許多功能，主要可以歸納為以下幾點：

- **開發階段的便利性**：
    - **開源組件與第三方整合**: LangChain 提供豐富的**開源組件**和與**第三方服務的整合**，方便開發者快速搭建應用程式。
    - **LangGraph**: 透過 **LangGraph** 可以建立具有即時串流和人機協作功能的**狀態代理**，這對於開發需要互動和即時回應的應用程式來說非常重要.
- **生產化階段的效率**：
    - **LangSmith**: 使用 **LangSmith** 進行應用程式的**檢查、監控和評估**，確保應用程式在部署前已經過最佳化。
- **部署階段的彈性**：
    - **LangGraph 平台**: 透過 **LangGraph 平台**，可以將 **LangGraph** 應用程式轉換為**生產就緒的 API 和助手**，方便應用程式的部署和使用。
- **標準化的介面**：
    - LangChain 為各種 LLM 和相關技術（如嵌入模型和向量儲存）提供**標準化的介面**，並與數百家供應商整合，讓您可以輕鬆地切換不同的模型和服務。
- **模組化和可組合性**:
    - **鏈 (Chains)**: LangChain 通過鏈的概念支持模組化和可組合性，讓您可以輕鬆地將不同的組件組合在一起，構建複雜的應用程式流程。
- **多個開源函式庫**:
    - **`langchain-core`**: 提供聊天模型和其他組件的基礎抽象。
    - **整合套件**: 重要的整合被拆分為輕量級套件，由 LangChain 團隊和整合開發人員共同維護，例如 `langchain-openai` 和 `langchain-anthropic`。
    - **`langchain`**: 包含構成應用程式認知架構的鏈、代理和檢索策略。
    - **`langchain-community`**: 由社群維護的第三方整合。
    - **`langgraph`**: 用於將 LangChain 組件組合到具有持久性、串流和其他關鍵功能的生產就緒應用程式的協調框架。

**LangChain 的應用方式**

LangChain 的應用範圍非常廣泛，以下是一些常見的應用場景：

- **聊天機器人**: 開發更智慧、更人性化的聊天機器人，並利用對話記憶來提升互動體驗。
- **生成式問答 (GQA)**: 建立可以根據給定內容回答問題的應用程式，並透過檢索增強來提高回答的準確性。
- **摘要**: 自動化文本摘要的過程，快速提取文章或文件的重點。
- **AI 代理**: 構建具有工具使用能力的 AI 代理，可以執行更複雜的任務，例如根據外部知識庫回覆問題。
- **RAG (Retrieval Augmented Generation)**: 利用 RAG 技術，結合檢索外部知識與生成文本，減少 LLM 的幻覺問題，並保持回答的時效性。
- **多查詢 RAG**: 在 RAG 流程中使用多個查詢，以便更全面地檢索相關資訊。

**LangChain 的學習資源**

LangChain 提供了豐富的學習資源，讓您可以快速上手：

- **教程 (Tutorials)**: 提供實作教學，適合想要動手實作特定應用程式的使用者。
- **操作指南 (How-to guides)**: 針對常見問題提供簡潔的解答，幫助您快速完成特定任務。
- **概念指南 (Conceptual guide)**: 提供 LangChain 所有關鍵概念的深入解釋。
- **整合 (Integrations)**: 列出與 LangChain 整合的工具，方便您快速上手使用聊天模型、向量儲存等組件。
- **API 參考 (API reference)**: 提供 LangChain Python 套件中所有類別和方法的完整文件，方便您深入了解程式碼的細節。
- **LangChain AI Handbook**: 提供對 LangChain 的全面介紹，並包含多個章節，涵蓋了各種主題，例如提示工程、鏈、對話記憶、檢索增強、AI 代理等。
- **LangChain Academy**: 提供 LangGraph 的入門課程，讓您可以更深入地了解 LangGraph 的概念和應用.
- **社群資源**: LangChain 擁有活躍的社群，您可以在論壇、社群媒體上找到許多有用的資源和協助。

**總結**

LangChain 是一個非常強大的框架，它可以幫助您快速開發出各種由 LLM 驅動的智慧應用程式。它具有**廣泛的整合、豐富的學習資源**和**強大的生態系統**，非常適合想要投入 LLM 開發的您。無論您是新手還是經驗豐富的開發者，都可以從 LangChain 中受益。希望這些資訊對您有所幫助！

![LangChain 介紹](https://github.com/user-attachments/assets/1b25ecee-3f37-4e67-94c0-94b97e436662)

