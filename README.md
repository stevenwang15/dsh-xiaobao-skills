# 消保技能目录（dsh-xiaobao-skills）

金融消保领域 AI 工作台的技能来源仓库。工作台每次按 `catalog.json` 读取并安装技能。

## 结构

- `catalog.json`：唯一真相源（技能清单 / 来源 / 安装方式 / 版本 / 校验）
- `skills/<id>/SKILL.md`：自研技能
- `dist/`（可选）：自研技能打包的 zip 与 sha256

## catalog 条目格式

```json
{
  "id": "complaint-timelimit",
  "name": "投诉时限核查",
  "category": "投诉管理",
  "tasks": ["定性", "时限计算", "逾期预警"],
  "installs": [
    { "type": "github-zip", "url": "https://…/complaint-timelimit-1.0.0.zip", "sha256": "…" },
    { "type": "skillhub", "namespace": "…", "skillId": "…", "version": "1.0.0" }
  ]
}
```

## 收录原则

- 只写引用，不复制他人技能正文
- 第三方技能指向原作者地址，并标注来源
- 每个条目必须有可校验的安装方式（github-zip 带 sha256 优先）
