# Happy-Horse-Shield-API
Happy Horse 1.0 多模态大模型防穿模隔离器引擎（API），含私有化部署Docker 镜像配置。
# Happy-Horse-Shield-API (ATH-DRIVE)

[ 特别声明：Alpha V1.0 架构预案 ]
本仓库目前提供的是底层防穿透路由 API 逻辑及云端算力调度架构。
鉴于 Happy Horse 1.0 官方权重将于 4月30日 正式开源，当前的 Docker 镜像依赖版本为理论推演环境。
建议：各位同行可先 Star 收藏并配置底层基础环境。请勿直接用于生产环境，最终实机压测微调版将于 4.30 模型释出后 24 小时内同步更新。欢迎提交 PR 参与共建。

---

专为 Happy Horse 1.0 多模态大模型设计的「防穿透隔离器 API」及私有化部署方案。

目前各大 AI 视频模型在处理大动态场景时，普遍存在结构崩坏、四肢畸变、背景穿模等痛点。本项目旨在底层模型与用户输入之间，构建一层强物理参数隔离墙。

## 核心特性 (V1.0)

* 提示词防穿透隔离：拦截危险提示词，强制注入 perfect anatomy, anti-distortion 等底层稳定权重。
* 极速异步并发接口：基于 FastAPI 构建，支持高并发，预留批量任务队列接口。
* 容器化一键部署：提供完整 Dockerfile 与 docker-compose，针对 NVIDIA RTX 4090 算力集群深度优化。
* 原生音视频同步支持：预留音频 Token 通道，迎接 4.30 模型全模态开源。

## 快速部署 (Docker 环境)

确保宿主机已安装 Docker 及 NVIDIA Container Toolkit。

```bash
# 1. 克隆仓库
git clone [https://github.com/你的用户名/Happy-Horse-Shield-API.git](https://github.com/你的用户名/Happy-Horse-Shield-API.git)
cd Happy-Horse-Shield-API

# 2. 启动算力集群调度
docker-compose up -d

# 3. 访问接口测试面板
[http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)
