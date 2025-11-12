# Bun React Demo

一个基于 [Bun](https://bun.sh/) 和 [React](https://react.dev/) 的全栈应用示例项目。展示了如何使用 Bun 作为运行时、构建工具和包管理器来构建现代化的 React 应用。

## 技术栈

- **Bun**: 最新版本 (JavaScript 运行时和工具链)
- **React**: 19.2
- **React DOM**: 19.2
- **Tailwind CSS**: 4.1.11
- **TypeScript**: 支持

## 项目结构

```
bun-react-demo/
├── src/
│   ├── index.ts         # 服务器入口，API 路由和静态文件服务
│   ├── index.html       # HTML 模板
│   ├── App.tsx          # React 主组件
│   ├── frontend.tsx     # 前端入口
│   ├── APITester.tsx    # API 测试组件
│   ├── index.css        # 全局样式
│   └── logo.svg         # 资源文件
├── build.ts             # 构建脚本
├── package.json         # 项目依赖配置
├── tsconfig.json        # TypeScript 配置
├── bunfig.toml          # Bun 配置文件
└── README.md
```

## 功能特性

- 全栈应用（前端 + 后端）
- React 19 支持
- Tailwind CSS 样式
- 热模块替换 (HMR)
- API 路由处理
- 静态文件服务
- TypeScript 支持

## 快速开始

### 前置要求

- [Bun](https://bun.sh/) 最新版本

### 安装和运行

```bash
# 克隆项目
git clone <repository-url>
cd bun-react-demo

# 安装依赖（Bun 会自动处理）
bun install

# 运行开发服务器
bun run dev
```

应用将在 `http://localhost:3000` 启动，支持热重载。
注：3000 端口是 bun 的默认端口。

### 生产构建

```bash
# 构建项目
bun run build

# 运行生产版本
bun run start
```

## API 端点

### Hello API
```http
GET http://localhost:3000/api/hello
PUT http://localhost:3000/api/hello
```
响应示例:
```json
{
  "message": "Hello, world!",
  "method": "GET"
}
```

### 带参数的 Hello API
```http
GET http://localhost:3000/api/hello/:name
```
响应示例:
```json
{
  "message": "Hello, Alice!"
}
```

## 代码说明

### 服务器 (`src/index.ts`)

Bun 服务器配置：
- **静态文件服务**: 所有未匹配的路由返回 `index.html`（支持 React Router）
- **API 路由**: `/api/hello` 和 `/api/hello/:name`
- **开发模式**: 启用 HMR 和浏览器控制台日志

### React 应用 (`src/App.tsx`)

主 React 组件：
- 展示 Bun 和 React 标志
- 包含 API 测试组件
- 使用 Tailwind CSS 进行样式设计

### API 测试组件 (`src/APITester.tsx`)

用于测试后端 API 的交互式组件。

## 开发特性

### 热模块替换 (HMR)

在开发模式下，修改代码会自动刷新浏览器，无需手动刷新。

### TypeScript 支持

项目完全使用 TypeScript 编写，提供类型安全。

### Tailwind CSS

使用 Tailwind CSS 4.x 进行样式设计，支持 JIT 编译。

## 构建和部署

### 构建

```bash
bun run build
```

构建脚本会：
- 编译 TypeScript
- 处理 React 组件
- 优化资源文件
- 生成生产就绪的构建

### 环境变量

可以通过环境变量配置：
- `NODE_ENV`: 设置为 `production` 以禁用开发特性

## 参考资源

- [Bun 官方网站](https://bun.sh/)
- [React 文档](https://react.dev/)
- [Tailwind CSS 文档](https://tailwindcss.com/)
