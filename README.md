<div align="center">

# 🍽️ Good Urban Eat

**基于 Spring Boot 的外卖业务后端系统**

[![Java](https://img.shields.io/badge/Java-Spring%20Boot-ED8B00?logo=openjdk)](https://www.java.com/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-2.7.3-6DB33F?logo=springboot&logoColor=white)](https://spring.io/projects/spring-boot)
[![MySQL](https://img.shields.io/badge/MySQL-8-4479A1?logo=mysql&logoColor=white)](https://www.mysql.com/)
[![Redis](https://img.shields.io/badge/Redis-cache-DC382D?logo=redis&logoColor=white)](https://redis.io/)

</div>

Good Urban Eat 是一个覆盖商家管理端与用户端业务的外卖服务后端。项目采用 Maven 多模块结构，包含商品、套餐、购物车、订单、支付、营业状态、数据报表与实时提醒等功能。

## 主要功能

- 员工登录、JWT 鉴权与后台权限拦截
- 分类、菜品、口味和套餐管理
- 用户地址簿、购物车和下单流程
- 订单状态流转、支付与退款接口
- 营业状态、定时任务和 WebSocket 实时提醒
- 营业额、订单量、用户量及销量排行报表
- 阿里云 OSS 文件存储与百度地图距离计算
- Knife4j 接口文档和统一异常处理

## 技术栈

| 模块 | 技术 |
| --- | --- |
| Web | Spring Boot 2.7.3, Spring MVC |
| 数据 | MySQL, MyBatis, PageHelper, Druid |
| 缓存 | Redis, Spring Cache |
| 鉴权 | JWT |
| 实时通信 | WebSocket |
| 工程 | Maven 多模块, Lombok, Knife4j |

## 项目结构

```text
Good-Urban-Eat/
├── sky-common/   # 公共配置、工具、常量与统一返回结构
├── sky-pojo/     # Entity、DTO、VO 与校验模型
├── sky-server/   # Controller、Service、Mapper 与应用入口
├── sky.sql       # 数据库初始化脚本
└── pom.xml       # Maven 父工程
```

## 本地启动

### 环境要求

- JDK 8 或更高版本
- Maven 3.6+
- MySQL 8
- Redis

### 启动步骤

1. 创建数据库并导入 `sky.sql`。
2. 在 `sky-server/src/main/resources/application-dev.yml` 中配置数据库、Redis 以及需要使用的第三方服务。
3. 构建并启动服务：

```bash
mvn clean package -DskipTests
java -jar sky-server/target/sky-server-1.0-SNAPSHOT.jar
```

服务默认运行在 `http://localhost:8080`。

> 请勿把真实数据库密码、云服务密钥或支付证书提交到仓库。生产环境应通过环境变量或独立配置中心注入敏感配置。

## 相关资料

- [数据库设计文档](数据库设计文档.md)
- `苍穹外卖-管理端接口.json`
- `苍穹外卖-用户端接口.json`

