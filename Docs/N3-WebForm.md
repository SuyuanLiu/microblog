# Web Form

Web Form 是 web application 中极为重要的一部分。使用 [Flask-WTF](https://flask-wtf.readthedocs.io/en/stable/)是 Flask 的一个扩展 extension。 Extensions 在 flask 中十分重要。下面介绍 Flask-WTF 的使用。

安装：(venv) \$ `pip install flask-wtf`

**配置**：Flask 给开发者很多自由，可以自行配置。在 config.py 文件中，定义一个 class 来存储配置变量。（代码见 config.py）定义的 SECRET_KEY 是 flask 应用中最重要的一个部分。flask 和它的一些扩展用这个变量来做 signature 或 token 的加密密钥。Flask-WTF 用它来保护 web form 免受 Cross-Site Request Forgery （CSRF）攻击。

SECRET_KEY 由两部分组成，一个是从环境中获取的环境变量，另一个是硬编码字符串。变量会先倾向于获取那个环境变量，如果环境没有给出对应的值，那么就直接使用硬编码字符串。如果你把代码部署到服务器上，一定要给出环境变量，这样更安全。
