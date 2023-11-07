# W-Assist

工作区智能助理。AI对话，文件摘要，图片生成，补全感知，内容解读，中英互译。
[去安装VS Code扩展](https://marketplace.visualstudio.com/items?itemName=kouyaqi.workspace-assistant)

## 功能
- AI聊天
    - 普通对话
    - 函数调用
        - 对文件提问
            - ![对文件提问](https://walkingon.github.io/gifs/w-assist/chat-file.gif)
        - 图片生成
            - ![图片生成](https://walkingon.github.io/gifs/w-assist/chat-img.gif)
- 补全感知
    - 文本补全
        - ![文本补全](https://walkingon.github.io/gifs/w-assist/completion-text.gif)
    - 代码补全
        - ![代码补全](https://walkingon.github.io/gifs/w-assist/completion-code.gif)
- 文本解读
    -  ![文本解读](https://walkingon.github.io/gifs/w-assist/explain.gif)
- 中英互译
    - ![中英互译](https://walkingon.github.io/gifs/w-assist/translate.gif)

## 使用方法
### 安装与设置
1. 从VS Code扩展商店搜索“W-Assist”安装。
2. 在安装后的扩展详情页点击“设置（齿轮图标）-> 扩展设置”。
3. 填写Key（必选），其他参数可以按需设置。[去获取Key](https://www.apiyin.com/merchant/853) 本扩展使用的Key不和其他应用兼容。
4. 扩展的所有功能均依赖Key中剩余的P点数，在聊天页面的右下角显示。
### 使用说明
- 聊天
    - 打开方式：在已打开的文件夹中，任一文档编辑窗口的右上角点击小幽灵图标。
    - 取消勾选“启用函数调用”会略微节约tokens的消耗，对话将不会给服务器发送函数信息，此时即普通对话。
    - 当前函数调用内置了2个功能。
        - 获取编辑器当前显示的文档内容
            - 没有参数
            - 触发词就简单讲“这个文件”即可
        - 图片生成
            - 参数
                - 对图片的描述
                - 生成图片数量，1~10张，默认为1
                - 图片尺寸，256、512、1024，默认1024。
            - 一张 256x256 的图片消耗 80P，512x512 的图片消耗 90P，1024x1024 的图片消耗 100P。
            - 后端最终服务由[OpenAI](https://platform.openai.com/docs/api-reference/images/create)提供。
    - 根据官方说法，较新的模型(gpt-3.5-turbo-0613和gpt-4-0613)对函数调用进行了微调，启用函数调用功能时建议选这两个模型。 [Function calling文档](https://platform.openai.com/docs/guides/gpt/function-calling)
    - 聊天页下方的点数不会实时刷新。
- 补全感知
    - 打开方式：任意正在编辑文件中右键菜单。
    - 首次点击功能开启，再次点击功能关闭。
    - 光标在一行文字末尾暂停数秒触发建议。
- 文本解读
    - 打开方式：选中一段文字右键菜单。
- 中英互译
    - 打开方式：选中一段文字右键菜单。

## 已知问题
1. 启用函数调用的情况下，对文件内容提问，有时AI并不一定会调用函数。
2. 选中日语文本使用“中英互译”获得的结果是英文，期望中文。
