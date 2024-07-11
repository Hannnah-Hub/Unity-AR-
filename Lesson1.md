# Lesson 1: 实现Player的移动
## Player自主地向前奔跑
```C#
public class PlayerMovement : MonoBehaviour
{
    void Update()
    {
        transform.Translate(0, 0, 1);
    }
}
```
### 代码逻辑：  
**transform：** 用来获取object的位置  
**Translate：** 用来移动object的位置  
**（0，0，1）：** 表示object的移动（x ,y ,z)  
在x轴方向移动0（不向左右移动），  
在y轴方向移动0（不向上下移动），  
在z轴方向移动1（向前移动1个单位）。  

## 再次修改
```C#
public class PlayerMovement : MonoBehaviour
{
    public float speed = 1.0f;

    void Update()
    {
        transform.Translate(0, 0, speed * Time.deltaTime);
    }
}
```
### 代码逻辑：  
**public float speed** 定义了一个值：“速度”，用来管控Object的移动速度倍率  
**deltaTime：** 确保了无论游戏以多少帧每秒运行，物体都以一致的速度移动  

## 3次修改
```C#
public class PlayerMovement : MonoBehaviour
{
    public float moveSpeed = 5f;

    void Update()
    {
        float moveX = Input.GetAxis("Horizontal");
        float moveZ = Input.GetAxis("Vertical");

        Vector3 move = new Vector3(moveX, 0, moveZ);
        transform.Translate(move * moveSpeed * Time.deltaTime, Space.World);
    }
}
```
### 代码逻辑
**moveSpeed：** 控制玩家的移动速度    
**Input.GetAxis("Horizontal") 和 Input.GetAxis("Vertical")：** 分别获取水平（A和D）和垂直（W和S）方向的输入   
**Vector3 move = new Vector3(moveX, 0, moveZ)：** 创建一个移动向量，X轴表示左右移动，Z轴表示前后移动   
**transform.Translate(move * moveSpeed * Time.deltaTime, Space.World)：** 根据输入和移动速度更新玩家的位置   

## 4次修改
```C#
public class PlayerMovement : MonoBehaviour
{
    public float moveSpeed = 5f;

    void Update()
    {
        float moveX = Input.GetAxis("Horizontal");
        float moveZ = Input.GetAxis("Vertical");

        Vector3 move = new Vector3(moveX, 0, 0);

        transform.Translate(move * moveSpeed * Time.deltaTime, Space.World);
    }
}
```
