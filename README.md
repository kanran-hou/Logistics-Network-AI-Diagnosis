# Logistics Network AI Diagnosis

基于空间统计与 AI 的全国快递网点布局诊断系统。

覆盖中国大陆 **31 个省级行政区、300 个城市**。

## 功能

- **全国覆盖**: 31省/直辖市/自治区，300地级市，2000+区县
- **网点地图**: Canvas渲染区县级色块密度图 + 散点标记
- **空间指标**: 核密度分析、标准差椭圆、最近邻距离
- **盲区识别**: 自动识别低密度区县
- **交通评估**: 交通网络密度、枢纽影响度
- **AI评分**: 布局/交通/均衡三维评分 (A/B/C/D)
- **分析报告**: 问题清单、优化建议、选址推荐

## 快速开始

```bash
cd express-analysis
pip install fastapi uvicorn httpx numpy loguru
uvicorn main:app --host 0.0.0.0 --port 8001
```

浏览器打开 http://localhost:8001

## 数据来源

- 快递网点数据: 各城市公开信息
- 行政区划边界: 阿里云DataV
- 交通数据: 基于城市特征估算

## 项目结构

```
express-analysis/
├── main.py              # FastAPI后端
├── express_data.json    # 300城市分析数据
├── process_data.py      # 数据处理脚本
├── templates/index.html # 前端页面
├── *_geo.json (299个)   # 行政区划边界
