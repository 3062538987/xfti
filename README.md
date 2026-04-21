# xfti 消费人格测试应用

一个基于前端技术开发的 xfbi 消费人格测试应用，帮助用户了解自己的消费行为模式。

## 功能特性

- 📝 **18道测试题目**：在原有14题基础上补充4题，提升维度稳定性
- 🎨 **美观界面**：现代化设计，渐变背景，响应式布局
- 💾 **本地存储**：支持测试进度保存，刷新页面后可继续测试
- 📊 **双层结果分析**：保留4大主类型，并新增5个子维度画像
- 🌐 **免费部署**：已部署到 Netlify，可直接访问

## 技术栈

- **前端**：纯 HTML、CSS、JavaScript
- **构建工具**：Vite
- **部署平台**：Netlify

## 本地开发

### 环境要求

- Node.js 16+
- npm 7+

### 安装依赖

```bash
cd client
npm install
```

### 启动开发服务器

```bash
npm run dev
```

访问 http://localhost:5173/ 查看应用

### 构建生产版本

```bash
npm run build
```

构建产物将生成在 `dist` 目录

## 部署

### Netlify 部署

#### 详细步骤

1. **安装 Netlify CLI**（如果尚未安装）：

   ```bash
   npm install -g netlify-cli
   ```

2. **登录 Netlify**：

   ```bash
   npx netlify login
   ```

   这会打开浏览器并引导您完成登录过程。

3. **构建项目**：

   ```bash
   npm run build
   ```

4. **部署到生产环境**：

   ```bash
   npx netlify deploy --site-name xfbi-test-app --dir=dist --prod --no-build
   ```

5. **查看部署状态**：
   部署完成后，Netlify CLI 会显示部署地址和相关信息。

#### 更新部署

当您对应用进行修改后，需要重新部署：

1. **重新构建**：

   ```bash
   npm run build
   ```

2. **重新部署**：
   ```bash
   npx netlify deploy --site-name xfbi-test-app --dir=dist --prod --no-build
   ```

#### 部署管理

- **查看部署历史**：访问 Netlify 控制台
- **修改站点设置**：在 Netlify 控制台中修改域名、构建配置等
- **查看访问统计**：Netlify 提供基本的访问统计功能

### 部署地址

- **Netlify**：https://xfbi-test-app-cb47bbdc.netlify.app

## 项目结构

```
xfbi-supabase/
├── client/
│   ├── dist/          # 构建产物
│   ├── node_modules/  # 依赖包
│   ├── index.html     # 主页面
│   ├── main.js        # 主要脚本
│   ├── style.css      # 样式文件
│   ├── package.json   # 项目配置
│   └── netlify.toml   # Netlify 配置
└── README.md          # 项目说明
```

## 测试说明

1. 打开应用后，点击「开始测试」按钮
2. 回答 18 道测试题目，每道题目有 4 个选项
3. 完成所有题目后，系统会自动计算主类型与子维度分数
4. 结果页面会显示消费人格主类型、描述和5维画像

## 结果类型

根据总分范围（18-72分），应用会生成四种消费人格主类型：

1. **🔪 我要把钱花在刀尖上！**（18-31分）
2. **⚔️ 我要把钱花在刀刃上！**（32-45分）
3. **✨ 我要把钱花在刀背上！**（46-59分）
4. **💸 我要把钱花在刀把上！**（60-72分）

## 子维度模型与评分逻辑

### 子维度定义（5维）

1. **D1 冲动触发敏感度**：越高表示越容易被限时、情绪、场景触发消费
2. **D2 预算与性价比执行**：越高表示预算纪律越强、比价意识越高
3. **D3 长期规划导向**：越高表示更偏长期目标、应急储备和延迟满足
4. **D4 关系与身份消费驱动**：越高表示更愿意为关系和身份表达买单
5. **D5 规则与正版合规倾向**：越高表示更偏向正版、规则和正规渠道

### 题目映射

- D1：Q1、Q5、Q6
- D2：Q2、Q3、Q4、Q12、Q13、Q16
- D3：Q8、Q14、Q15
- D4：Q7、Q11、Q17
- D5：Q9、Q10、Q18

### 选项计分方式

- 每题4个选项在维度中对应权重：`-2 / -1 / +1 / +2`
- 每题只映射到一个主维度
- 特殊题可配置 `0` 分权重（当前Q2、Q3含中性选项）

### 维度标准化公式

- 维度原始分：该维度下所有题权重求和
- 维度最小分：`-2 × 该维度题数`
- 维度最大分：`+2 × 该维度题数`
- 标准化：`(原始分 - 最小分) / (最大分 - 最小分) × 100`

结果页会按标准化分（0-100）展示每个维度的进度条与倾向描述（高/中/低）。

### 代码位置

- 题库与补充题：`client/index.html` 中 `questions` 数组
- 维度模型：`client/index.html` 中 `dimensionModel`
- 题目维度映射：`client/index.html` 中 `dimensionQuestionMap`
- 维度计算函数：`client/index.html` 中 `calculateDimensionScores()`
- 维度渲染函数：`client/index.html` 中 `renderDimensionScores()`

## 贡献

欢迎提交 Issue 和 Pull Request 来改进这个项目！

## 许可证

MIT License
