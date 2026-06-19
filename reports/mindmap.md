# GUI 语义认知框架 — 思维导图（200 样本扩展阶段）

> 阶段定位：已有 GUI 语义认知框架的「数据扩展 + 鲁棒性验证」阶段
> （未改架构、未改 13 类标签、未训练模型）。最终数据集 = **恰好 200 条样本**。

## 一、整体思维导图（Mermaid）

```mermaid
mindmap
  root((GUI 语义认知<br/>200 样本))
    管线 Pipeline
      未知 GUI
      自主探索 Playwright
      交互证据 before/after + DOM
      语义归纳 13 类
      知识图谱 NetworkX
      零样本泛化
    环境 5 个
      GitHub 42 实采
      Wikipedia 40 实采
      Notion 50 实采
      YouTube 40 复用旧数据·网络阻断
      Google Drive 28 复用旧数据·网络阻断
    动作 Action
      click 127
      hover 73
    语义标签 13 类
      出现 7 类
        menu 137
        profile 22
        home 12
        setting 10
        search 9
        edit 6
        favorite 4
      未出现 6 类
        notification
        share
        download
        upload
        filter
        bookmark
    缩放结论 25→200
      标签覆盖 7/13 稳定
      平均置信度 0.63→0.57
      置信度标准差 0.16→0.15 收紧
      归一化熵 0.66→0.45 趋稳
      5 环境全程保留
```

## 二、数据流（Mermaid 流程图）

```mermaid
flowchart LR
  A[未知 GUI 网站] --> B[自主探索<br/>Playwright]
  B --> C[交互证据<br/>before/after 截图 + 视觉差分 + DOM 增量]
  C --> D[语义归纳<br/>证据规则 / Qwen2.5-VL]
  D --> E[知识图谱<br/>概念→可见性→子功能]
  E --> F[零样本泛化<br/>未见 GUI 图标预测]
  F --> G[200 样本数据集<br/>+ 10 图 + 报告]
```

---

## 三、核心结果图片（点击可看大图）

### 1. 数据集统计
![dataset_statistics](../figures/dataset_statistics.png)

### 2. 语义类别分布（13 类中出现 7 类）
![category_distribution](../figures/category_distribution.png)

### 3. 跨环境语义分布
![cross_environment_distribution](../figures/cross_environment_distribution.png)

### 4. 置信度分布
![confidence_distribution](../figures/confidence_distribution.png)

### 5. 缩放曲线 25 → 200（稳定性 & 覆盖率）
![scaling_curve](../figures/scaling_curve.png)

### 6. 知识图谱（思维导图式本体）
![knowledge_graph](../figures/knowledge_graph.png)

### 7. Before / After 交互网格
![before_after_grid](../figures/before_after_grid.png)

### 8. 语义示例网格
![semantic_examples_grid](../figures/semantic_examples_grid.png)

### 9. 失败 / 低证据样例
![failure_cases](../figures/failure_cases.png)

### 10. 零样本泛化 Demo
![generalization_demo](../figures/generalization_demo.png)

---

## 四、文件位置速查

| 类型 | 路径 |
|------|------|
| 200 样本（严格 schema） | `dataset/processed/samples.jsonl` |
| 管线轨迹 | `dataset/processed/trajectories.jsonl` |
| 元素级语义 | `results/semantics.json` |
| 缩放指标 | `dataset/processed/scaling_metrics.json` |
| 10 张要求图片 | `figures/*.png` |
| 知识图谱 | `semantic_graph/semantic_knowledge_graph.png` |
| 缩放分析 | `reports/scaling_analysis.md` |
| 数据/实验/PPT 报告 | `reports/dataset_summary.md` · `experiment_analysis.md` · `ppt_material.md` |
| 本思维导图 | `reports/mindmap.md` |

> 说明：YouTube / Google Drive 在采集网络下被阻断（`ERR_CONNECTION_CLOSED`），
> 这两个环境复用既有原始交互；其余三站为本机实采。menu 占主导与「未登录落地页
> 以导航链接为主」一致；登录态可surface更多类别（notification/share/upload 等）。
