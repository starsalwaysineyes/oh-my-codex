# oh-my-codex

一组针对 Codex 工作流本土化后的技能集合（非 Claude Code 语法）。

## 包含技能

- `analyze`
- `autopilot`
- `build-fix`
- `code-review`
- `deepsearch`
- `learner`
- `note`
- `plan`
- `ralph`

## 目录结构

```text
skills/
  analyze/SKILL.md
  autopilot/SKILL.md
  build-fix/SKILL.md
  code-review/SKILL.md
  deepsearch/SKILL.md
  learner/SKILL.md
  note/SKILL.md
  plan/SKILL.md
  ralph/SKILL.md
```

## 本地安装（手动）

```bash
# 在 Codex 工作机上执行
mkdir -p ~/.codex/skills
cp -R skills/* ~/.codex/skills/
```

## 说明

这些技能已去除 Claude Code 专属调用（如 `/oh-my-claudecode:*`、`Task(...)`、`AskUserQuestion` 等），改为 Codex 可执行语义（如 `rg`、`functions.exec_command`、`multi_tool_use.parallel`、`update_plan`）。

## 致谢

本项目在思路和部分技能组织方式上参考了 [oh-my-claudecode](https://github.com/Yeachan-Heo/oh-my-claudecode)，并针对 Codex 工作流做了本土化调整。
