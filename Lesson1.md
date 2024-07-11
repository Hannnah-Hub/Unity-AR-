# Lesson 1: 实现Player的移动
## Player自主地向前奔跑
```C#
    void Update()
    {
        transform.Translate(0, 0, 1);
    }
}
```
代码逻辑：
transform组件用来获取object的位置
Translate用来移动object的位置
（0，0，1）表示object的移动（x ,y ,z)
在x轴方向移动0（不向左右移动），
在y轴方向移动0（不向上下移动），
在z轴方向移动1（向前移动1个单位）。
