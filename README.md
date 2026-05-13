# WorkBuddy Skills

个人 WorkBuddy 自定义技能仓库，存放各类实用 Skills。

## 仓库结构

```
workbuddy-skills/
├── README.md              # 本文件
└── skill-template/        # Skill 模板
    ├── SKILL.md          # 技能文档
    ├── scripts/          # 可执行脚本
    ├── references/       # 参考文档
    └── assets/          # 资源文件
```

## 已收录 Skills

### skill-template

通用 Skill 模板，用于快速创建新的 WorkBuddy Skills。

**包含内容：**
- 标准化的 SKILL.md 模板
- 完整的 skill 开发指南
- 脚本/参考文档/资源文件模板
- 验证和打包说明

**使用方法：**
1. 复制 `skill-template` 目录并重命名
2. 编辑 SKILL.md 和内容
3. 运行 `package_skill.py` 打包

## Skill 开发

### 创建新 Skill

```bash
# 使用 skill-creator 初始化
python ~/.workbuddy/plugins/marketplaces/cb_teams_marketplace/plugins/skill-creator/scripts/init_skill.py <skill-name> --path .

# 验证
python ~/.workbuddy/plugins/marketplaces/cb_teams_marketplace/plugins/skill-creator/scripts/quick_validate.py <skill-name>

# 打包
python ~/.workbuddy/plugins/marketplaces/cb_teams_marketplace/plugins/skill-creator/scripts/package_skill.py <skill-name>
```

### 安装 Skill

将 skill 目录复制到 `~/.workbuddy/skills/` 即可使用。

## 相关资源

- [WorkBuddy 文档](https://www.codebuddy.cn/docs/workbuddy/)
- [Skill 开发指南](https://www.codebuddy.cn/docs/workbuddy/skills)

## 许可证

MIT License
