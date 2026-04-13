# xfbi 消费人格测试应用

一个基于前端技术开发的 xfbi 消费人格测试应用，帮助用户了解自己的消费行为模式。

## 功能特性

- 📝 **14道测试题目**：涵盖各种消费场景，全面分析消费人格
- 🎨 **美观界面**：现代化设计，渐变背景，响应式布局
- 💾 **本地存储**：支持测试进度保存，刷新页面后可继续测试
- 📊 **结果分析**：根据得分生成详细的消费人格分析报告
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
2. 回答 14 道测试题目，每道题目有 4 个选项
3. 完成所有题目后，系统会自动计算得分并显示结果
4. 结果页面会显示您的消费人格类型和详细分析

## 结果类型

根据得分范围，应用会生成四种消费人格类型：

1. **🔪 我要把钱花在刀尖上！**（14-24分）
2. **⚔️ 我要把钱花在刀刃上！**（25-35分）
3. **✨ 我要把钱花在刀背上！**（36-46分）
4. **💸 我要把钱花在刀把上！**（47-56分）

## 贡献

欢迎提交 Issue 和 Pull Request 来改进这个项目！

## 许可证

MIT License
