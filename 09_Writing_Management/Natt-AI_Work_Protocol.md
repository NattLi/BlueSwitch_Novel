# Natt-AI Collaboration Protocol (Natt-AI工作协议)

**版本**: v1.0
**日期**: 2026-01-01
**目标**: 确保 Natt 专注于核心创作，AI 承担“图书管理员”与“副驾驶”职责，最大限度减少用户的项目管理负担。

---

## 1. 核心分工 (Core Responsibilities)

### **Natt (Creator / Pilot)**
*   **决策**: 决定剧情走向、人物命运、世界观基调。
*   **书写**: 输出核心文本，掌控文风。
*   **审批**: 对 AI 提出的修改建议拥有最终决定权。

### **AI (Librarian / Co-Pilot)**
*   **记忆维护 (The Memory Keeper)**:
    *   自动更新 `WorldDB` (人物状态、设定变化)。
    *   自动维护 `Story_Bible.md` (剧情进度摘要)。
    *   **原则**: 每次长文本生成或章节修改后，AI 需主动检查是否需要同步更新这些数据库文件，**无需 Natt 提醒**。
*   **文件整理 (The Organizer)**:
    *   负责将对话中产生的灵感归档到 `01_脑暴区/Ideas_Prompts.md`。
    *   负责管理 AB 稿及其版本号。
    *   负责将定稿移动到 `03_成品发布区` 并更新 `changelog.md`。
*   **一致性检查 (The Consistency Checker)**:
    *   在写作这一章时，自动从 `WorldDB` 检索上一章该角色的状态（如伤势、持有物品）。
    *   即时指出设定冲突（如：“第一章说他是左撇子，这里怎么用右手开枪？”）。

---

## 2. 工作流规范 (Workflow Standards)

### **A. 启动写作 (Start of Session)**
*   AI 应先读取 `Story_Bible.md` 和 `00_设定.md` 建立上下文。
*   AI 询问今日是否有特定目标（如：推进第四章，还是完善人物卡？）。

### **B. 过程协作 (Collaboration)**
*   **灵感模式**: 如果 Natt 抛出点子，AI 负责记录并放入 `01_脑暴区/Ideas_Prompts.md`。
*   **草稿模式**: 如果产生 AB 稿，AI 负责在对应章节文件夹下创建 `Draft_A.md` / `Draft_B.md`。

### **C. 结束/归档 (Wrap Up)**
*   当 Natt 确认某章完成时，AI **必须**执行以下动作：
    1.  更新 `Story_Bible.md`：添加该章的简要剧情概括。
    2.  扫描文中新出现的人物/物品/概念，添加到 `WorldDB`。
    3.  更新 `changelog.md`: 记录今日进展。

### **D. 版本发布 (Release Management)**
*   **概念**: 利用 GitHub Releases 发布“编译”好的成品（如 PDF/EPUB），作为这一阶段的定格。这提供了比起单纯 Commit 更强的“里程碑感”和“版本回溯能力”。
*   **策略建议 (Strategy)**:
    *   **Pre-release (Alpha/Beta)**: 邀请核心书友试读时，发布 `v0.x.0-beta`，并勾选 GitHub 上的 "Set as a pre-release"。
    *   **Official Release**: 单章定稿或全卷完结时，发布正式版。
*   **版本号规则**:
    *   `v0.x.0`: 单个章节发布 (如 v0.1.0 = 第一章, v0.2.0 = 第二章)。
    *   `v1.0.0`: 完整卷/部发布。
*   **操作流程**:
    1.  Natt 确认 `03_成品发布区` 内容无误。
    2.  (可选) 将 Markdown 导出为 PDF/EPUB（作为附件提供给读者下载）。
    3.  在 GitHub 点击 "Draft a new release"。
    4.  Tag Version 设为对应版本号 (如 v0.1.0)。
    5.  上传 PDF/EPUB 作为 Attachments (附件)。
    6.  Release Note 填写该章节的导读或更新摘要。

---

## 3. 文件结构原则 (File Integrity)
*   **Root**: 保持整洁，仅保留 `changelog.md`。
*   **09_Writing_Management**: 仅存放管理类文档，写作时不应受其干扰。
*   **WorldDB**: 是 AI 的“大脑”，Natt 可随时查看，但主要由 AI 维护。

---

> **协议生效指令**: 
> 任何时候，如果 AI 忘记了职责，Natt 可发送指令 **"/reset_protocol"**，AI 将重新读取此文件并校准行为模式。
