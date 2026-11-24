---
name: explain-python-traceback
description: Use when a learner shares a Python traceback or exception and asks what caused it or what to try first. 适用于 Python 报错解读。
---

# Python 报错解读

先从异常类型和消息确定出错的操作。沿 traceback 找到用户能修改的位置，并区分触发异常的那一行和真正产生坏数据的位置。有异常链时，解释哪个异常先发生、后来哪个异常被抛出。

用三段回答：报错是什么意思、哪些证据能定位原因、最小验证或修复是什么。遇到 `KeyError` 时，先核对缺失的键和输入结构。只有业务上允许缺失时才建议设置默认值。信息不够时，指出缺哪一行代码或哪一项运行时的值。

示例：`user["age"]` 抛出 `KeyError: 'age'`。先查看失败样本是否含有 `age`。如果年龄必填，修正上游数据或验证输入。如果年龄选填，可以用 `user.get("age")`，并让下游处理 `None`。
