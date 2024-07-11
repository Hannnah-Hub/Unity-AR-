# Lesson 1: 实现Player的移动
## Player自主地向前奔跑
```C#
    void Update()
    {
        transform.Translate(0, 0, 1);
    }
}
```
### 代码逻辑：  
1.transform组件用来获取object的位置  
2.Translate用来移动object的位置  
3.（0，0，1）表示object的移动（x ,y ,z)  
在x轴方向移动0（不向左右移动），  
在y轴方向移动0（不向上下移动），  
在z轴方向移动1（向前移动1个单位）。  

## 再次修改
```C#
    public float speed = 1.0f;

    void Update()
    {
        transform.Translate(0, 0, speed * Time.deltaTime);
    }
}
```
代码逻辑：  
1.定义了一个值：“速度”，用来管控Object的移动速度倍率  
2.deltaTime：确保了无论游戏以多少帧每秒运行，物体都以一致的速度移动  
