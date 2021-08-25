&emsp;&emsp;时序图（Sequence Diagram），又名序列图、循序图、顺序图，是一种UML交互图。它通过描述对象之间发送消息的时间顺序显示多个对象之间的动态协作。它可以表示用例的行为顺序，当执行一个用例行为时，其中的每条消息对应一个类操作或状态机中引起转换的触发事件。

样例1：

```html
@startuml

A -> B : text1
B --> A : text2
'这里是注释
/'这里是可换行的
注释'/

@enduml
```

效果：

<img src="https://gitee.com/lrk612/md_picture/raw/master/img/20210825123356.png" alt="image-20210825105656559" width="15%" />

&nbsp;

样例2：加上消息序号

```
@startuml

autonumber
'这个关键字可自动为消息加序号
A -> B : text1
B --> A : text2

autonumber 5 10
'也可以用于指定序号
A -> B : text3
B --> A : text4

@enduml
```

效果：

<img src="https://gitee.com/lrk612/md_picture/raw/master/img/20210825123357.png" alt="image-20210825111226804" width="15%" />

&nbsp;

样例3：加上消息注释

```html
@startuml

A -> B : text1
note left: comment1

B --> A : text2
note right: comment2

A -> B : text3
note left: comment3

B --> A : text4
note right: comment4

@enduml
```

效果：

<img src="https://gitee.com/lrk612/md_picture/raw/master/img/20210825123358.png" alt="image-20210825112152648" width="30%" />

&nbsp;

样例4：加上消息者注释

```html
@startuml

participant A
participant B

rnote left of A
comment on A left 1
comment on A left 2
end note
'多行注释这样写

note right of B: comment on B right
'单行注释这样写

note over A: comment on A head

hnote over A, B
comment for A and B
on there head
end note

@enduml
```

效果：

<img src="https://gitee.com/lrk612/md_picture/raw/master/img/20210825123359.png" alt="image-20210825113055800" width="40%" />

&nbsp;

样例5：使用html标签

```html
@startuml

participant A
participant B

note left of A: <size:20>comment on A left 1</size>
'字体大小
note left of A: ~~comment on A left 2~~
'波浪线
note right of B: comment on --删除部分-- B right
'消息者注释删除线
note right of B: picture <img library.JPG>
'插入图片

A -> B : **text1**
'加粗
B --> A : ~~text2~~
'下划线
A -> B : <color red>text3</color>
'字体颜色
B --> A : <s:black>text4</s>
'消息删除线


@enduml
```

效果：

![image-20210825120605218](https://img-blog.csdnimg.cn/img_convert/e7e45fb167a8bdca3bbd15db36200413.png)

&nbsp;

样例6：划分阶段

```html
@startuml

==阶段一==
A -> B : text1
B --> A : text2

==阶段二==
A -> B : text3
B --> A : text4

@enduml
```

效果：

<img src="https://gitee.com/lrk612/md_picture/raw/master/img/20210825123401.png" alt="image-20210825120927516" width="10%" />

&nbsp;

样例7：延时

```html
@startuml

...100 years later...
A -> B : text1
B --> A : text2

...200 years later...
A -> B : text3
B --> A : text4

@enduml
```

效果：

<img src="https://gitee.com/lrk612/md_picture/raw/master/img/20210825123402.png" alt="image-20210825121326063" width="10%" />

&nbsp;

样例：加入间隔

```html
@startuml

A -> B : text1
B --> A : text2

|||
A -> B : text3
B --> A : text4

||60||
'指定间隔长度
A -> B : text3
B --> A : text4

@enduml
```

效果：

<img src="https://gitee.com/lrk612/md_picture/raw/master/img/20210825123403.png" alt="image-20210825122232668" width="10%" />

&nbsp;

样例：消息者组合

```html
@startuml

box "组合1" #LightBlue
participant A
participant B
end box
'组合A、B，并以蓝色为底色

A -> B : text1
B -> C : text2

@enduml
```

效果：

<img src="https://gitee.com/lrk612/md_picture/raw/master/img/20210825123404.png" alt="image-20210825122610329" width="20%" />

&nbsp;

样例8：加入标题和隐藏底部对象

```html
@startuml

hide footbox
'隐藏底部对象

title "标题1"

A -> B : text1
B --> A : text2

@enduml
```

效果：

<img src="https://gitee.com/lrk612/md_picture/raw/master/img/20210825123405.png" alt="image-20210825122941222" width="12%" />

&nbsp;

样例：

```html
@startuml

participant par
actor A
boundary B
control C
entity E
database D
'上面几个是不同类型的事先声明，声明的变量具有不同图案

par->A : to actor
par->B : to boundary
par->C : to control
par->E : to entity
par->D : to database

@enduml
```

效果：

<img src="https://gitee.com/lrk612/md_picture/raw/master/img/20210825123406.png" alt="image-20210825110640942" width="40%" />

&nbsp;

&nbsp;

&nbsp;

&emsp;&emsp;此外PlantUML还可用于绘制用例图、类图、流程图、组件图、状态图、对象图等，以后用到了再补充。
