# HANDOFF

## 2026-10-25：Fork 与后续修改准备

- 用户已在服务器上验证原版插件可用，本轮授权创建 fork，为后续修改做准备。
- Fork：https://github.com/KirishimaRin/astrbot_plugin_findchicken
- 原仓库：https://github.com/ALpapam/astrbot_plugin_findchicken
- 本地目录：E:\Project\astrbot_plugin_findchicken
- origin 指向用户 fork；upstream 指向原仓库；初始基线提交 08c6ace，插件版本 1.0.0。
- 尚未修改插件代码，尚未将服务器上的插件切换为 fork。后续先根据用户的新要求确定修改内容。
- 固定文案位于 findchicken/formatter.py。metadata.yaml 中的 repo 当前仍是原仓库地址；发布修改版时需核对更新来源并保留原作者署名。
- 不在仓库中保存 SSH 密码、SauceNAO API Key、QQ 消息记录或服务器配置。

## 已遇到的工具问题

- 当前 gh 版本在指定源仓库参数时，不支持同时使用 --remote；使用 `gh repo fork ALpapam/astrbot_plugin_findchicken --clone` 即可创建 fork、克隆并设置 origin/upstream。

## 2026-10-25：kfc50 指令与搜索提示

- 用户指定触发指令为 kfc50，说明为「kfc50：引用/附带图片或发送图片链接，搜索图片来源。」，搜索提示为「🐔 正在寻找，请稍等…」。
- 同步修改标准指令注册、QQ 引用消息兜底正则、无图用法提示、README 与配置说明。结果标题、字段和底部提示保留原版。
- 修改指令时务必同步 QQ 引用消息的兜底匹配，否则普通消息可用而引用图片仍匹配旧指令。
- 版本更新为1.0.1，metadata.yaml 的 repo 指向用户 fork，保留原作者署名和 README 上游链接。
- 验证：python -m pytest -q，40 passed；git diff --check 通过。没有增加网络请求、依赖或后台任务。
- 服务器尚未安装本次修改版。
