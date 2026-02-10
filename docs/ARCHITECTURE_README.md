# KubeSphere 架构文档 / Architecture Documentation

本目录包含 KubeSphere 项目的详细架构分析文档。

This directory contains detailed architecture analysis documents for the KubeSphere project.

## 📚 文档列表 / Document List

### 1. 架构分析.md (Chinese)
**完整的中文架构分析文档**

包含内容：
- 项目概述和核心特性
- 详细的项目结构说明
- 微内核 + 扩展组件架构解析
- API 架构和数据模型
- 控制器架构和工作原理
- 认证授权机制
- 扩展机制详解
- 多集群架构
- DevOps 集成
- 可观测性方案
- 安全特性
- 性能和规模指标
- 部署方式
- 技术亮点总结

### 2. ARCHITECTURE_ANALYSIS.md (English)
**Complete English architecture analysis document**

Covers:
- Project overview and core features
- Detailed project structure
- Microkernel + Extension Components architecture
- API architecture and data models
- Controller architecture and patterns
- Authentication and authorization
- Extension mechanisms
- Multi-cluster architecture
- DevOps integration
- Observability solutions
- Security features
- Performance and scale metrics
- Deployment methods
- Technical highlights

### 3. ARCHITECTURE_DIAGRAMS.md (Bilingual)
**架构图解文档 / Architecture Diagrams**

包含以下架构图：
Contains the following diagrams:

1. **总体架构 / Overall Architecture**
   - 展示系统各层次和组件关系
   - Shows system layers and component relationships

2. **微内核架构 / Microkernel Architecture**
   - KubeSphere Core + Extensions 设计
   - KubeSphere Core + Extensions design

3. **API 架构 / API Architecture**
   - API 层次和路由机制
   - API layers and routing mechanisms

4. **多租户架构 / Multi-Tenancy Architecture**
   - 三层租户模型和 RBAC
   - Three-tier tenant model and RBAC

5. **控制器协调循环 / Controller Reconciliation Loop**
   - Kubernetes 控制器模式
   - Kubernetes controller pattern

6. **多集群架构 / Multi-Cluster Architecture**
   - 主集群和成员集群关系
   - Host and member cluster relationships

7. **DevOps 流水线 / DevOps Pipeline**
   - CI/CD 流程图
   - CI/CD workflow

8. **存储架构 / Storage Architecture**
   - CSI 驱动和存储类
   - CSI drivers and storage classes

9. **网络架构 / Network Architecture**
   - Service Mesh 和 CNI
   - Service Mesh and CNI

10. **监控和日志架构 / Monitoring & Logging Architecture**
    - 可观测性完整方案
    - Complete observability solution

## 🎯 快速导航 / Quick Navigation

### 想了解什么？/ What do you want to know?

#### 🏗️ **架构设计 / Architecture Design**
- 微内核 + 扩展组件模式 → [架构分析.md](./架构分析.md#3-核心架构) / [ARCHITECTURE_ANALYSIS.md](./ARCHITECTURE_ANALYSIS.md#3-core-architecture)
- 架构图示 → [ARCHITECTURE_DIAGRAMS.md](./ARCHITECTURE_DIAGRAMS.md)

#### 🔧 **核心组件 / Core Components**
- ks-apiserver 详解 → [架构分析.md](./架构分析.md#321-ks-apiserver)
- ks-controller-manager 详解 → [架构分析.md](./架构分析.md#322-ks-controller-manager)

#### 🌐 **API 设计 / API Design**
- API 层次和模块 → [架构分析.md](./架构分析.md#4-api-架构)
- API 架构图 → [ARCHITECTURE_DIAGRAMS.md](./ARCHITECTURE_DIAGRAMS.md#3-api-架构--api-architecture)

#### 👥 **多租户 / Multi-Tenancy**
- 多租户模型 → [架构分析.md](./架构分析.md#52-多租户层级)
- 多租户架构图 → [ARCHITECTURE_DIAGRAMS.md](./ARCHITECTURE_DIAGRAMS.md#4-多租户架构--multi-tenancy-architecture)

#### 🎛️ **控制器 / Controllers**
- 控制器模式 → [架构分析.md](./架构分析.md#6-控制器架构)
- 控制器协调图 → [ARCHITECTURE_DIAGRAMS.md](./ARCHITECTURE_DIAGRAMS.md#5-控制器协调循环--controller-reconciliation-loop)

#### 🔐 **安全 / Security**
- 认证授权机制 → [架构分析.md](./架构分析.md#7-认证和授权)
- 安全特性 → [架构分析.md](./架构分析.md#12-安全性)

#### 🔌 **扩展 / Extensions**
- 扩展机制 → [架构分析.md](./架构分析.md#8-扩展机制)
- 微内核架构图 → [ARCHITECTURE_DIAGRAMS.md](./ARCHITECTURE_DIAGRAMS.md#2-微内核架构--microkernel-architecture)

#### 🌍 **多集群 / Multi-Cluster**
- 多集群管理 → [架构分析.md](./架构分析.md#9-多集群架构)
- 多集群架构图 → [ARCHITECTURE_DIAGRAMS.md](./ARCHITECTURE_DIAGRAMS.md#6-多集群架构--multi-cluster-architecture)

#### 🚀 **DevOps**
- DevOps 集成 → [架构分析.md](./架构分析.md#11-devops-集成)
- DevOps 流水线图 → [ARCHITECTURE_DIAGRAMS.md](./ARCHITECTURE_DIAGRAMS.md#7-devops-流水线--devops-pipeline)

#### 📊 **可观测性 / Observability**
- 监控和日志 → [架构分析.md](./架构分析.md#10-可观测性)
- 监控架构图 → [ARCHITECTURE_DIAGRAMS.md](./ARCHITECTURE_DIAGRAMS.md#10-监控和日志架构--monitoring--logging-architecture)

## 📖 文档使用建议 / Documentation Usage Guide

### 对于新手 / For Beginners
1. 先阅读项目概述部分，了解 KubeSphere 是什么
2. 查看架构图，建立整体概念
3. 深入阅读感兴趣的模块详解

Start by reading the project overview to understand what KubeSphere is, then view the architecture diagrams to get the big picture, and finally dive into specific modules of interest.

### 对于开发者 / For Developers
1. 重点关注 API 架构和控制器章节
2. 查看代码结构和主要包的说明
3. 参考扩展机制了解如何开发扩展组件

Focus on API architecture and controller sections, review code structure and main packages, and refer to extension mechanisms for developing extensions.

### 对于架构师 / For Architects
1. 深入研究微内核架构设计
2. 了解多租户和多集群方案
3. 评估安全性和可扩展性特性

Study the microkernel architecture design in depth, understand multi-tenancy and multi-cluster solutions, and evaluate security and scalability features.

## 🎨 文档特色 / Document Features

### ✅ 全面性 / Comprehensive
- 覆盖 KubeSphere 所有核心架构层面
- 从宏观到微观的多层次分析
- Covers all core architecture aspects of KubeSphere
- Multi-level analysis from macro to micro

### 🖼️ 可视化 / Visual
- 丰富的 ASCII 架构图
- 清晰的层次关系展示
- Rich ASCII architecture diagrams
- Clear hierarchical relationship displays

### 🌐 双语 / Bilingual
- 中英文对照
- 适合国际化团队
- Chinese-English parallel text
- Suitable for international teams

### 📝 详实 / Detailed
- 详细的代码路径说明
- 实际的配置示例
- 清晰的数据流程
- Detailed code path descriptions
- Actual configuration examples
- Clear data flow explanations

## 🔄 文档更新 / Document Updates

**当前版本 / Current Version**: 1.0  
**KubeSphere 版本 / KubeSphere Version**: 4.1.2  
**最后更新 / Last Updated**: 2026-02-10

本文档将随着 KubeSphere 版本更新而持续维护。

This documentation will be continuously maintained as KubeSphere versions are updated.

## 🤝 贡献 / Contributing

如果您发现文档中的错误或有改进建议，欢迎提交 Issue 或 Pull Request。

If you find errors in the documentation or have suggestions for improvement, please submit an Issue or Pull Request.

## 📚 更多资源 / More Resources

- [KubeSphere 官方文档 / Official Documentation](https://kubesphere.io/docs/)
- [KubeSphere GitHub](https://github.com/kubesphere/kubesphere)
- [KubeSphere 社区 / Community](https://github.com/kubesphere/community)
- [开发指南 / Developer Guide](https://github.com/kubesphere/community/tree/master/developer-guide/development)
- [扩展开发指南 / Extension Development Guide](https://dev-guide.kubesphere.io/extension-dev-guide/)

---

**欢迎探索 KubeSphere 的架构世界！**

**Welcome to explore the architectural world of KubeSphere!**
