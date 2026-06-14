# Claude Code 项目四件套实操配置指南

这是一个面向本地项目的 Claude Code 使用指南仓库，重点解决四件事：

1. 项目要做什么
2. Claude Code 应该怎么工作
3. 项目当前做到哪
4. 每次任务应该怎么下达

## Python 项目统一约定

本指南中的 Python 项目统一使用 [`uv`](https://docs.astral.sh/uv/) 管理 Python 版本、虚拟环境和依赖：

```bash
uv python install 3.11
uv sync
uv add <package>
uv run pytest
```

新项目使用 `pyproject.toml` 和 `uv.lock`，不再同时维护多套包管理或虚拟环境方案。

## 快速开始

如果你想直接拿去用，按这个顺序走就够了：

1. 先看 [`面向OPC的claudecode使用指南.md`](./面向OPC的claudecode使用指南.md)
2. 复制并填写 [`docs/project_brief.md`](./docs/project_brief.md)
3. 根据自己的项目调整 [`CLAUDE.md`](./CLAUDE.md)
4. 复制 [`docs/project_status.md`](./docs/project_status.md) 作为长期记录
5. 每次任务都按指南里的固定模板下达

## 仓库结构

```text
.
├── CLAUDE.md
├── README.md
├── docs/
│   ├── project_brief.md
│   ├── project_status.md
│   └── examples/
│       ├── sample_project_brief.md
│       └── sample_project_status.md
└── 面向OPC的claudecode使用指南.md
```

## 仓库内容

- [`面向OPC的claudecode使用指南.md`](./面向OPC的claudecode使用指南.md): 完整说明文档
- [`CLAUDE.md`](./CLAUDE.md): 项目级行为规范
- [`docs/project_brief.md`](./docs/project_brief.md): 项目需求基线
- [`docs/project_status.md`](./docs/project_status.md): 项目状态记录
- [`docs/examples/sample_project_brief.md`](./docs/examples/sample_project_brief.md): 已填写的需求样例
- [`docs/examples/sample_project_status.md`](./docs/examples/sample_project_status.md): 已填写的状态样例

## 你可以怎么用

### 作为新项目模板

1. 复制 `docs/project_brief.md`
2. 复制 `docs/project_status.md`
3. 按自己的业务替换示例内容
4. 把 `CLAUDE.md` 改成适合你团队或个人习惯的版本

### 作为已有项目整理模板

1. 先让 Claude 只读分析现有项目
2. 再反向生成 `project_brief`
3. 初始化 `project_status`
4. 后续每次任务都按模板记录

## 适合谁

- 想把 Claude Code 用在本地 Python 项目上的个人开发者
- 想减少上下文丢失和误改风险的人
- 想把需求、规则、状态分开管理的人

## 示例文件说明

`docs/examples/` 里的文件不是额外需求，而是“填好后的参考答案”。
你可以直接照着改，不需要从空白页开始。
