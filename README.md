# GraphRAG Test Project

## 简介

这个项目是GraphRAG系统的测试实现，使用Ollama作为本地LLM和嵌入模型。GraphRAG是一个强大的工具，用于索引文本数据并基于索引数据回答问题。

## 特性

- 使用Ollama作为本地LLM和嵌入模型
- 支持文本索引和查询
- 可配置的索引和查询参数
- 支持本地搜索和全局搜索

## 快速开始

### 前提条件

- Python 3.10-3.12
- Ollama安装并运行在本地（http://127.0.0.1:11434）

### 安装

1. 克隆仓库：
   ```
   git clone https://github.com/PCcoding666/GraphRAG_Test.git
   cd GraphRAG_Test
   ```

2. 安装依赖：
   ```
   pip install graphrag
   ```

### 配置

项目使用`settings.yaml`文件进行配置。主要配置包括：

- LLM设置：使用Ollama的qwen2:7b模型
- 嵌入设置：同样使用Ollama的qwen2:7b模型
- 索引和查询参数

### 运行索引器

1. 准备输入数据：
   ```
   mkdir -p ./ragtest/input
   curl https://www.gutenberg.org/cache/epub/24022/pg24022.txt > ./ragtest/input/book.txt
   ```

2. 运行索引器：
   ```
   python -m graphrag.index --root ./ragtest
   ```

### 使用查询引擎

1. 全局搜索示例：
   ```
   python -m graphrag.query --root ./ragtest --method global "What are the top themes in this story?"
   ```

2. 本地搜索示例：
   ```
   python -m graphrag.query --root ./ragtest --method local "Who is Scrooge, and what are his main relationships?"
   ```

## 项目结构

- `ragtest/`: 主项目目录
  - `input/`: 输入文本文件
  - `output/`: 索引输出和报告
  - `settings.yaml`: 配置文件

## 贡献

欢迎提交问题和拉取请求来改进项目。

## 许可证

[在此添加许可证信息]

## 致谢

- GraphRAG项目
- Ollama项目