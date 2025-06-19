# 测试数据生成工具集

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://license/)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)]()
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)]()
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)]()

一套用于生成测试数据的Web工具，包含身份证号码生成器和用户信息生成器。

## 功能特性

### 身份证号码生成器

- ✅ 生成符合规则的虚拟身份证号码  
- ✅ 可自定义出生地、出生日期、性别  
- ✅ 支持批量生成（1-50个）  
- ✅ 一键复制功能  
- ✅ 导出为文本文件  

### 用户信息生成器

- ✅ 生成多样化虚拟用户信息  
- ✅ 支持生成以下数据类型：
  - 姓名、年龄、性别  
  - 地址、手机号、电子邮箱  
  - 银行卡号（借记卡/信用卡）  
  - 身份证号、公司名称、职位  
  - 学历、婚姻状况、年收入  
  - 个人网站、微博账号、QQ号  
- ✅ 灵活选择需要生成的数据类型  
- ✅ 批量生成（1-10条）  
- ✅ 一键复制和导出功能  

## 技术栈

- **前端**：HTML5, CSS3, JavaScript  
- **UI框架**：Bootstrap 5  
- **图标库**：Font Awesome 6  
- **依赖管理**：CDN引入  

## 快速开始

### 1. 环境准备

确保已安装以下软件：

- [Nginx](https://nginx.org/) 或其他 Web 服务器  
- 现代浏览器（Chrome/Firefox/Edge等）

### 2. 部署步骤

1. 克隆或下载本仓库  
2. 将 HTML 文件放入 Web 服务器目录（如 Nginx 的 `html` 目录）  
3. 配置 Nginx（参考下方配置示例）  
4. 启动 Web 服务器  

### Nginx 配置示例

```nginx
server {
    listen       80;
    server_name  localhost;

    location / {
        root   /path/to/your/html;
        index  idcard.html userInfo.html;
    }

    # 用户信息生成器页面
    location /userinfo {
        alias   html;  # 确保路径与 root 目录一致
        index  userInfo.html;
    }

    # 身份证生成器页面
    location /idcard {
        alias   html;  # 确保路径与 root 目录一致
        index  idcard.html;
    }

    error_page   500 502 503 504  /50x.html;
    location = /50x.html {
        root   html;
    }
}

```

 ### 3. 访问应用

- 身份证生成器：`http://139.155.148.195/userinfo`
- 用户信息生成器：`http://139.155.148.195/idcard`

## 使用说明

1. **身份证生成器**：
   - 选择出生地（省/市/区县）
   - 设置出生日期（年/月/日）
   - 选择性别和生成数量
   - 点击"开始生成"按钮
   - 使用"复制全部"或点击单个身份证号复制
2. **用户信息生成器**：
   - 在顶部选择需要生成的数据类型
   - 设置生成参数（数量、年龄范围、性别等）
   - 点击"开始生成"按钮
   - 使用"复制全部"或点击单条信息复制
   - 可导出为文本文件

