---
name: skill-template
description: 通用 Skill 模板，用于快速创建新的 WorkBuddy Skills。当用户需要创建新 skill 或需要 skill 模板时使用此技能。此模板提供了标准化的 skill 结构、最佳实践指南和可定制的代码框架。
---

# Skill 模板

## 概述

此技能提供了一个通用的 WorkBuddy Skill 模板，帮助快速创建符合规范的自定义技能。模板包含标准化的文件结构、frontmatter 元数据、以及可扩展的代码框架。

## 何时使用此技能

- 需要创建新的 WorkBuddy Skill
- 需要参考标准化的 skill 结构
- 需要了解 skill 开发的最佳实践
- 需要可定制的 skill 代码框架

## Skill 结构

```
skill-name/
├── SKILL.md           # 必需：技能主体文档
├── scripts/           # 可选：可执行脚本
├── references/        # 可选：参考文档
└── assets/           # 可选：资源文件
```

## 快速开始

### 1. 基础模板使用

复制此模板并重命名目录为你的技能名称。

### 2. 配置 SKILL.md

编辑 SKILL.md 的 frontmatter：

```yaml
---
name: your-skill-name
description: 详细描述此技能的用途和触发场景
---
```

### 3. 编写技能内容

按照以下结构组织 SKILL.md：

- **概述** (Overview)：简要说明技能用途
- **触发条件** (When to Use)：明确何时应该使用此技能
- **工作流程** (Workflow)：分步骤说明操作流程
- **示例** (Examples)：提供具体使用示例

## 核心部分

### 工作流程设计

根据技能类型选择合适的工作流程结构：

**顺序流程** - 适用于多步骤任务
```markdown
## 工作流程

### 步骤 1: 准备
- 描述步骤 1 的操作

### 步骤 2: 执行
- 描述步骤 2 的操作
```

**任务分类** - 适用于多种操作类型
```markdown
## 任务

### 任务类型 A
- 描述任务 A 的处理方式

### 任务类型 B
- 描述任务 B 的处理方式
```

### 脚本集成

如果技能需要可执行脚本，在 `scripts/` 目录中添加：

```python
# scripts/your_script.py
# 描述: 脚本功能说明
# 用法: python scripts/your_script.py [参数]
```

在 SKILL.md 中引用脚本：
```markdown
使用 `scripts/your_script.py` 执行 [具体任务]。
```

### 参考文档

如果技能需要详细的参考文档，在 `references/` 目录中添加：

- API 文档
- 数据库 schema
- 公司规范
- 技术文档

在 SKILL.md 中引用：
```markdown
详细规范参见 `references/your_reference.md`。
```

## 最佳实践

### 内容编写

- 使用祈使句（动词开头）
- 保持客观、指导性语言
- 避免重复信息
- 将详细信息放在 references/ 中

### 触发条件

在 description 中明确说明触发场景：
- 具体的用户请求模式
- 相关的文件类型
- 特定的任务类型

### 资源管理

- 将可复用代码放在 scripts/
- 将参考文档放在 references/
- 将输出资源放在 assets/
- 保持 SKILL.md 简洁（<5k 词）

## 示例

### 示例 1: 简单技能

```markdown
---
name: hello-world
description: 简单的示例技能，用于演示基础结构
---

# Hello World 技能

## 概述

此技能提供基础的 "Hello World" 功能演示。

## 何时使用

当用户请求简单的问候或演示时。

## 工作流程

1. 接收用户请求
2. 返回 "Hello, World!"
```

### 示例 2: 带脚本的技能

```markdown
---
name: file-processor
description: 处理特定文件类型的技能，包含可执行脚本
---

# 文件处理技能

## 概述

处理 [特定文件类型] 的创建、编辑和分析。

## 何时使用

- 用户需要创建 [文件类型]
- 用户需要编辑 [文件类型]
- 用户需要分析 [文件类型]

## 工作流程

### 创建文件

使用 `scripts/create_file.py` 创建新文件：

\`\`\`bash
python scripts/create_file.py --output output.file --data "数据"
\`\`\`

### 编辑文件

使用 `scripts/edit_file.py` 编辑现有文件...
```

## 验证与打包

完成技能开发后：

1. **验证技能**：
   ```bash
   python path/to/skill-creator/scripts/quick_validate.py path/to/your-skill
   ```

2. **打包技能**：
   ```bash
   python path/to/skill-creator/scripts/package_skill.py path/to/your-skill
   ```

## 资源

此技能包含以下模板资源：

### scripts/

包含示例脚本框架，可根据需要定制或删除。

### references/

包含参考文档模板，用于存放详细的规范或文档。

### assets/

包含资源文件模板，用于存放输出所需的文件。

---

**根据实际需要删除不必要的目录。** 并非每个技能都需要所有三类资源。
