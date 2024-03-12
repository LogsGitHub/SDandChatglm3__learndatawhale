# Datawhale 社区 ChatGLM、SD项目实践活动学习笔记（第一部分）

本笔记是参与Datawhale社区ChatGLM、SD项目实践活动的第一部分的记录，主要对学习笔记中未详细说明且我好奇的内容进行额外的资料查阅与补充，以加深理解和掌握。使用了驱动云平台进行项目的运行和实验。

活动内容的详细信息可以在以下链接中找到：[Datawhale ChatGLM、SD项目实践](https://datawhaler.feishu.cn/docx/BwjzdQPJRonFh8xeiSOcRUI3n8b)
## 一、如何设置镜像源

- 使用`git config`命令设置Git操作的镜像源。例如，使用`git config --global url."https://gitclone.com/".insteadOf https://`命令可以让Git在进行clone和fetch操作时，自动将`https://`替换为`https://gitclone.com/`，这对于在访问速度慢或受限的地区尤其有用。
- 通过`pip config`命令设置Python包安装器（pip）使用的包索引镜像源，如`pip config set global.index-url https://pypi.virtaicloud.com/repository/pypi/simple`命令。这可以加速包的安装过程，特别是在默认的PyPI服务器访问缓慢或被限制的情况下。
- 使用`python3 -m pip install --upgrade pip`命令升级pip到最新版本，以确保有最新的功能和安全修复。

## 二、启动服务器的两种方式及其异同

- 第一种方式：`demo.launch(server_name="127.0.0.1", server_port=7870, inbrowser=True, share=False)`。这种方式将服务器绑定在本地主机，仅允许从同一台机器上访问，适用于本地测试。
- 第二种方式：`demo.queue().launch(share=False, server_name="0.0.0.0", server_port=7000)`。与第一种方式不同，这种方式将服务器绑定在所有网络接口上，使其可以从网络中的任何机器上访问。此外，它引入了队列系统处理请求，更适合处理多个请求或用户。

两种方式的主要区别在于可访问性和并发处理能力。第二种方式因其更广泛的网络可访问性和更好的请求管理而更适合实际应用。

## 三、云计算平台中的“添加外部端口映射”的作用

- “添加外部端口映射”允许从外部网络通过公共IP地址和端口访问内部网络中的服务。这对于使云环境中托管的服务可从互联网访问至关重要。
- 它提供了访问控制，安全隔离，并允许解决端口冲突问题，同时提供服务抽象和灵活性，因为可以在不改变用户访问方式的情况下更改内部网络结构。

## 四、使用Gradio或基于Streamlit为创建交互式Web演示有什么不同

- **Gradio**专为快速创建机器学习模型演示而设计，易于使用，支持多种输入和输出类型，适合非技术用户。
- **Streamlit**提供更多控制和定制能力，适用于创建更复杂的交互式Web应用程序。它允许开发者利用更广泛的小部件和组件来增强用户交互和数据可视化。

Gradio适合于需要快速原型和展示模型的场景，而Streamlit则更适合需要构建更为复杂和定制化的应用程序的场景。
