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

---

## 3. 文件结构原则 (File Integrity)
*   **Root**: 保持整洁，仅保留 `changelog.md`。
*   **09_Writing_Management**: 仅存放管理类文档，写作时不应受其干扰。
*   **WorldDB**: 是 AI 的“大脑”，Natt 可随时查看，但主要由 AI 维护。

---

> **协议生效指令**: 
> 任何时候，如果 AI 忘记了职责，Natt 可发送指令 **"/reset_protocol"**，AI 将重新读取此文件并校准行为模式。
