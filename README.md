# NeuraLab - AI 模型训练控制台（真实训练版）

一个专业深色 IDE 风格的 AI 训练控制台，**在浏览器中用 TensorFlow.js 进行真实神经网络训练**（WebGL 加速、真实反向传播），不是模拟数据。

## 快速开始

无需安装，直接用浏览器打开 `index.html`（需联网加载 Tailwind / ECharts / TensorFlow.js CDN）。

或本地起服务：

```bash
python -m http.server 8899
# 访问 http://localhost:8899/index.html
```

部署：整个文件夹上传到 GitHub Pages 等静态托管即可。

## 真实在哪里

- 真实模型：TF.js Sequential MLP，结构可调（4 → 64x3 层），编译时真实计算参数量
- 真实优化：SGD / Adam / AdamW，可调学习率、batch、epochs，含 15% 验证集
- 真实数据：螺旋 / 双月 / XOR 分类、正弦回归，或上传你自己的 CSV（最后一列标签，本地处理不上传）
- 真实反馈：每个 epoch 的真实 loss / accuracy / val_loss 曲线，实时决策边界 / 拟合曲线
- 真实产物：训练完导出 model.json + weights.bin，可在任何 TF.js 项目加载使用

## 操作

- 按钮：选数据集 → 调参数 → 开始 / 暂停（保留权重可续训）/ 停止 → 导出模型
- 命令行：`train --epochs 100 --lr 0.01`、`pause`、`resume`、`stop`、`status`、`summary`、`eval`、`export`、`ls tasks|datasets`、`clear`

## 已验证

浏览器实测：螺旋分类 80 epochs，loss 0.0327，训练集准确率 98.8%。

## 技术栈

HTML + Tailwind CSS + ECharts + TensorFlow.js 4.17（均 CDN），单文件。
