## shortcut

| shortcut     | description                                          |
| ------------ | ---------------------------------------------------- |
| iter+tab     | foreach statement，live template                     |
| ctrl+alt+<-  | prev position                                        |
| ctrl+-       | 折叠代码                                             |
| ctrl++       | 展开代码                                             |
| shift*2      | search everywhere                                    |
| ctrl+o       | override method                                      |
| ctrl+i       | implement                                            |
| alt+insert   | generate common methods,such as ctor,test method     |
| ctrl+R       | search and replace                                   |
| ctrl+alt+m   | move to method                                       |
| Alt+Insert   | in pom.xml search dependency and add dependency node |
| ctrl+shift+U | taggle case（uppercase or lowercase）                |



### Function Shortcut

| shortcut | description                                          |
| -------- | ---------------------------------------------------- |
| F2       | next tips                                            |
| F3       | search,equal Ctrl+F                                  |
| F4       | go to definition                                     |
| F5       | Copy class                                           |
| F6       | Move object                                          |
| F7       | on debug mode,go to next step                        |
| F8       | on debug mode,go to next step,don't into function    |
| F9       | on debug mode,go to next breakpoints,or run continue |
| F11      | bookmark 书签,or use [Ctrl+F11]()                    |
| F12      | open bottom panel                                    |

* iter foreach template



## Debug

| shortcut         | description                                              |
| ---------------- | -------------------------------------------------------- |
| Shift+F9         | 进入调试                                                 |
| Shift+F10        | 直接运行，不调试                                         |
| F7               | 下一步，如果断点在方法上，则进入方法体                   |
| F8               | 下一步，不进入方法                                       |
| F9               | 恢复运行或跳到下一断点                                   |
| Alt+F8           | 弹出监视窗口                                             |
| Ctrl+F8          | 设置断点/去掉断点                                        |
| Shift+F7         | 智能步入。断点所在行上有多个方法调用，会弹出进入哪个方法 |
| Shift+F8         | 相当于F9                                                 |
| Ctrl+Shift+F8    | 指定断点条件进入                                         |
| Drop Frame       | 回退重来（IDEA的一个按钮）                               |
| Mute Breakpoints | 禁用所有断点（IDEA功能）                                 |
|                  |                                                          |



## ctrl+

| 快捷键           | 介绍                                                         |
| ---------------- | ------------------------------------------------------------ |
| Ctrl + F         | 在当前文件进行文本查找 `（必备）`                            |
| Ctrl + R         | 在当前文件进行文本替换 `（必备）`                            |
| Ctrl + Z         | 撤销 `（必备）`                                              |
| Ctrl + Y         | 删除光标所在行 或 删除选中的行 `（必备）`                    |
| Ctrl + X         | 剪切光标所在行 或 剪切选择内容                               |
| Ctrl + C         | 复制光标所在行 或 复制选择内容                               |
| Ctrl + D         | 复制光标所在行 或 复制选择内容，并把复制内容插入光标位置下面 `（必备）` |
| Ctrl + W         | 递进式选择代码块。可选中光标所在的单词或段落，连续按会在原有选中的基础上再扩展选中范围 `（必备）` |
| Ctrl + E         | 显示最近打开的文件记录列表 `（必备）`                        |
| Ctrl + N         | 根据输入的 **类名** 查找类文件 `（必备）`                    |
| Ctrl + G         | 在当前文件跳转到指定行处                                     |
| Ctrl + J         | 插入自定义动态代码模板 `（必备）`                            |
| Ctrl + P         | 方法参数提示显示 `（必备）`                                  |
| Ctrl + Q         | 光标所在的变量 / 类名 / 方法名等上面（也可以在提示补充的时候按），显示文档内容 |
| Ctrl + U         | 前往当前光标所在的方法的父类的方法 / 接口定义 `（必备）`     |
| Ctrl + B         | 进入光标所在的方法/变量的接口或是定义处，等效于 `Ctrl + 左键单击` `（必备）` |
| Ctrl + K         | 版本控制提交项目，需要此项目有加入到版本控制才可用           |
| Ctrl + T         | 版本控制更新项目，需要此项目有加入到版本控制才可用           |
| Ctrl + H         | 显示当前类的层次结构                                         |
| Ctrl + O         | 选择可重写的方法                                             |
| Ctrl + I         | 选择可继承的方法                                             |
| Ctrl + +         | 展开代码                                                     |
| Ctrl + -         | 折叠代码                                                     |
| Ctrl + /         | 注释光标所在行代码，会根据当前不同文件类型使用不同的注释符号 `（必备）` |
| Ctrl + [         | 移动光标到当前所在代码的花括号开始位置                       |
| Ctrl + ]         | 移动光标到当前所在代码的花括号结束位置                       |
| Ctrl + F1        | 在光标所在的错误代码处显示错误信息 `（必备）`                |
| Ctrl + F3        | 调转到所选中的词的下一个引用位置 `（必备）`                  |
| Ctrl + F4        | 关闭当前编辑文件                                             |
| Ctrl + F8        | 在 Debug 模式下，设置光标当前行为断点，如果当前已经是断点则去掉断点 |
| Ctrl + F9        | 执行 Make Project 操作                                       |
| Ctrl + F11       | 选中文件 / 文件夹，使用助记符设定 / 取消书签 `（必备）`      |
| Ctrl + F12       | 弹出当前文件结构层，可以在弹出的层上直接输入，进行筛选       |
| Ctrl + Tab       | 编辑窗口切换，如果在切换的过程又加按上delete，则是关闭对应选中的窗口 |
| Ctrl + End       | 跳到文件尾                                                   |
| Ctrl + Home      | 跳到文件头                                                   |
| Ctrl + Space     | 基础代码补全，默认在 Windows 系统上被输入法占用，需要进行修改，建议修改为 `Ctrl + 逗号``（必备）` |
| Ctrl + Delete    | 删除光标后面的单词或是中文句 `（必备）`                      |
| Ctrl + BackSpace | 删除光标前面的单词或是中文句 `（必备）`                      |
| Ctrl + 1,2,3...9 | 定位到对应数值的书签位置 `（必备）`                          |
| Ctrl + 左键单击  | 在打开的文件标题上，弹出该文件路径 `（必备）`                |
| Ctrl + 光标定位  | 按 Ctrl 不要松开，会显示光标所在的类信息摘要                 |
| Ctrl + 左方向键  | 光标跳转到当前单词 / 中文句的左侧开头位置 `（必备）`         |
| Ctrl + 右方向键  | 光标跳转到当前单词 / 中文句的右侧开头位置 `（必备）`         |
| Ctrl + 前方向键  | 等效于鼠标滚轮向前效果 `（必备）`                            |
| Ctrl + 后方向键  | 等效于鼠标滚轮向后效果 `（必备）`                            |