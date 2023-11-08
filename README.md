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
    - 聊天页下方的点数不会实时刷新。
    - 取消勾选“启用函数调用”会略微节约tokens的消耗，对话将不会给服务器发送函数信息，此时即普通对话。
    - 函数调用内置了2个功能。
        1. 获取编辑器当前显示的文档内容
            - 没有参数
            - 触发词就简单讲“这个文件”即可
        2. 图片生成（v0.7.0版起更新为DALL·E 3模型）
            - 'dall-e-3'单次只能生成一张图片。了解：[OpenAI文档](https://platform.openai.com/docs/api-reference/images/create)
            - 参数（怎么利用参数？例如可以讲“生成一张小猫的图片，高清，大小1792x1024，自然样式”，除了图片描述其他参数都是可选的）
                - [必要]对图片的描述
                - 图像质量，可以是'standard', 'hd', 默认为'standard'。
                - 图片尺寸，'1024x1024'，'1792x1024'，'1024x1792'，默认为 '1024x1024'。
                - 生成图像的样式，可以是'vivid'超现实和戏剧性，'natural'更自然，默认为'vivid'
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
