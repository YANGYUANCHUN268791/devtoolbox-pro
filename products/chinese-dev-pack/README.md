# 使用 Express 构建开发者工具箱：15个实用工具一站式搞定

## 技术选型
- Express.js 4.x（Node.js 后端框架）
- EJS 模板引擎
- Helmet（安全头）
- express-rate-limit（限流）
- Compression（Gzip压缩）
- Morgan（日志）

## 核心架构

### API 设计
每个工具就是一个纯函数，接受输入返回输出。

```javascript
const tools = {
  json: {
    name: "JSON Formatter",
    fn: (input) => JSON.stringify(JSON.parse(input), null, 2)
  },
  base64Encode: {
    name: "Base64 Encode",
    fn: (input) => Buffer.from(input).toString("base64")
  },
  // ... 共15个工具
};
```

### 路由设计
POST /api/tool/:toolName - 调用工具
GET /api/tools - 列出所有工具
GET /health - 健康检查

### 安全措施
- Helmet 安全头
- 请求频率限制（15分钟100次）
- 输入大小限制（5MB）
- 全局错误处理

## 部署方式

### 方式1：Node.js 直接部署
```bash
npm install
npm start
```

### 方式2：Docker
```dockerfile
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install --production
COPY . .
EXPOSE 3000
CMD ["node", "server.js"]
```

### 方式3：静态 HTML（单体版本）
不需要服务器的纯前端版本，打开即用。

## 完整源码
GitHub: github.com/YANGYUANCHUN268791
商业授权请联系：cao63571@gmail.com

---

如果你觉得这个项目有用，欢迎点赞收藏。Pro版提供更多高级功能，仅199元。
