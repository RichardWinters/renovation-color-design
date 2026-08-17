# 贡献指南

感谢你愿意为 `renovation-color-design` Skill 添砖加瓦。

这个 Skill 是把装修设计经验沉淀成可复用的工作流。任何人都可以贡献色号、风格模板、地区避坑指南或决策表修正。

## 行为准则

- 友善、专业、就事论事
- 不接受人身攻击、性别歧视、地域歧视
- 设计观点可以讨论，但不 diss 别人的实际居住环境
- 所有贡献默认采用 MIT 协议

## 提交流程

### 1. Fork + 克隆

```bash
# 在 GitHub 上点 Fork 按钮
git clone https://github.com/<your-username>/renovation-color-design.git
cd renovation-color-design
git remote add upstream https://github.com/RichardWinters/renovation-color-design.git
```

### 2. 拉取最新主分支

```bash
git checkout main
git pull upstream main
```

### 3. 创建特性分支

```bash
git checkout -b feat/<type>-<short-name>
# type 取值：color / style / region / fix / docs
# 例：feat/color-add-farrow-ball / fix-style-table-error
```

### 4. 提交（提交信息规范见下）

```bash
git add <files>
git commit -m "<type>(<scope>): <subject>"
# 例：color(wall): add Farrow & Ball Estate 系列 12 色
git push origin feat/<your-branch>
```

### 5. 在 GitHub 上开 PR

- 标题：和提交信息一致
- 描述：写明改了什么、为什么改、有没有实拍验证
- 如果涉及色号，必须附实拍色块照片（自然光下）

## 提交信息规范

采用 Conventional Commits 风格：

```
<type>(<scope>): <subject>

<body>

<footer>
```

| type | 含义 |
|------|------|
| `feat` | 新增功能（新风格、新色号、新章节） |
| `fix` | 修正错误（错色号、错尺寸、错判断） |
| `docs` | 文档修改（README、SKILL.md、CONTRIBUTING） |
| `refactor` | 重构（不改变行为的结构调整） |
| `chore` | 杂项（拼写、链接、格式） |

| scope | 说明 |
|-------|------|
| `wall` | 墙漆色号 |
| `floor` | 地板/瓷砖 |
| `stone` | 岩板/石材 |
| `cabinet` | 柜门/板材 |
| `metal` | 五金/灯具 |
| `style` | 风格模板 |
| `region` | 地区避坑 |
| `texture` | 表面质感决策 |

**示例：**

```
feat(wall): add Farrow & Ball Estate 系列 12 色

补充英系高端墙漆色号，覆盖以下场景：
- 冷调白：Ammonite, Pavilion Blue, Pigeon
- 暖调白：Slipper Satin, Dimity, Joa's White
- 深色：Inchyra Blue, Vardo, Studio Green

所有色号都附了 RGB 换算和对应立邦/多乐士近似色。

# 请审核
```

## 各类型贡献的具体要求

### A. 提新色号

格式（PR 描述中按表格列）：

| 色号 | 中文名 | RGB | 适用风格 | 适用位置 | 近似替代 |
|------|--------|-----|----------|----------|----------|

要求：
- 来源品牌（立邦/多乐士/芬琳/F&B 等）
- 实拍色块照片（自然光、白墙对比、灰墙对比各一张）
- RGB 换算公式
- 至少 1 个使用案例

### B. 提新风格模板

按 SKILL.md 的"风格速查表"格式补全：

```
| 风格名 | 主色 + 色号 | 辅色 + 色号 | 点缀 + 色号 | 代表场景 | 关键材质 |
```

要求：
- 风格有清晰的视觉调性（不能跟现有 5 个重复）
- 至少 2 个实装案例（小红书/酷家乐链接 + 截图）
- 主材/辅材/灯光全套给出

### C. 提新地区避坑

按 `references/regional-tips.md` 现有结构补：

```
## <地区名>
### 气候特点
- ...
### 适配材料调整
- ...
### 禁用材料
- ...
```

要求：
- 真实居住在那个地区
- 至少 1 个踩坑实例

### D. 修正决策表

直接 PR 改 `references/design_principles.md`，提交信息写清楚：
- 原判断是什么
- 改成了什么
- 为什么要改（实测/案例/官方资料）

## 审核标准

PR 会被以下条件驳回：

- 色号无实拍（屏幕截图不算）
- 风格无案例链接
- 提交信息不符合规范
- 引入未经验证的小红书爆款（变数太大）
- 涉及政治、宗教、地域歧视

PR 会被合并：

- 满足格式要求
- 有实际证据（实拍/官方资料/案例链接）
- 通过本地 quick_validate.py 校验

## 本地校验

提交前跑一下：

```bash
python ~/.workbuddy/plugins/cache/workbuddy-builtin/skill-skill-creator/0.1.0/scripts/quick_validate.py .
```

通过后才推。

## 发布节奏

- 新色号/小修正：随时合
- 新风格/新地区：满 5 个 PR 触发一次版本号 bump
- 大改：开 Issue 讨论后再动

## 版权

所有贡献默认采用 [MIT License](LICENSE)。

## 联系方式

- 提 Issue：GitHub Issues
- 紧急：直接 @ 维护者

---

_这份规范会随社区反馈调整。觉得有不合理的，提 PR 改它。_
