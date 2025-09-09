## CMD
1. 盘符+冒号，盘符切换
2. dir,查看当前路径下的内容
3. cd目录，进入单级目录
4. cd..退回上一级目录
5. cd 目录1/目录2 进入多级目录
6. cd\ 回退到盘符目录
7. cls 清屏
8. exit退出命令提示符窗口
建立环境变量：在高级系统设置，系统变量中添加path
## IDEA

## java
工具分类：javac java jdb：调试工具  jhat：内存分析工具
1. javac 文件名.java  \建立class文件，然后才可以用java运行
2. java 文件名  \运行文件内容 
3. 注释：单行注释: //，多行注释: /*  */，文档注释: /**     */     可用注释调试代码
4. 关键字： 被java赋予了特点含义的英文单词   关键字全部小写 

### 字面量
1. 整数类型： 不带小数点的数字
2. 小数类型： 带小数
3. 字符串类型： 双引号
4. 字符类型：单引号 ，内容只有一个
5. 布尔类型：true false
6. 空类型：一个特殊的空值
7. \t 制表符： 在打印的时候，把前面字符串的长度补齐到8或8的倍数，最少补一个最多补八个。
### 变量
1. 不能重复定义（有 int 时）
2. 修改变量值：直接赋值然后覆盖掉
3. 变量的作用域范围
4. 变量使用前一定要赋值
### 进制
1. 二进制：0b开头
2. 十进制：无前缀
3. 八进制：0开头
4. 十六进制：0x开头
### 运算符
1. 在代码中，如果有小数参与计算，会有可能不精确的。
2. 隐式转换：把小的转成大的数据 byte < short < int < long < float < double   byte、short、char会先变成int 类型再进行计算。
3. 强制转换：大给小，不允许直接赋值： 目标数据类型 变量名 = 被强制的数据
4. 三元运算符：关系表达式？表达式1：表达式2
### 数组
1. 存储同种类型的多个值，要考虑隐式转换
2. 数组类型 【】 数组名///数据类型 数组名【】
3. 输出数组的话直接是地址值。16进制
4. 访问：数组索引
5. 长度：lens 数组名.length  ////idea: 数组名。fori
6. 初始话只制定数组长度，有系统分配初始值。格式： 数据类型[] 数组名 = new 数据类型[数组长度]
### 方法
1. 是程序中最小的执行单元
2. 格式：
```java
public static void 方法名（参数a,参数b）{
方法体
}
```
1. 形参：方法定义的参数。
2. 实参：调用的参数。
```java
public static 返回值类型 方法名（参数a,参数b）{
方法体
return 返回值;
}
```
1. 方法重载：方法名可以一致，但是形参不可以一样。不同定义：个数、类型、顺序
## class
1. 创建一个类
### scanner
1. import java.util.Scanner;
2. Scanner sc = new Scanner(System.in);
3. int i = sc.nextInt()
### Random
1. import java.util.Random;
2. Random r = new Random();
3. int i = r.nextInt(随机数的范围)；0~number-1
### 打印
1. println //换行打印
2. print //不换行          print +‘ ' //出现空格
### 循环
1. 例子
```java
for(int i = 0, j = arr.length-1;i<j;i++;j++){}
```

```java
  
package bao;  
public class xunhuan {  
    public static void main(String[] args) {  
        int count = 0;  
        for (int i = 101; i <=201; i++) {  
            boolean flag  = true;  
            for (int j = 2; j <i; j++) {  
                if (i%j==0) {  
                    flag = false;  
                    //break 跳出单层循环  
                    break;  
                }  
            }  
            if(flag){  
                count++;  
                System.out.print(i+", ");  
            }  
        }  
        System.out.println("其中的质数数为："+ count);  
    }  
}
```

#### 定义一个随机的五位的验证码，验证码格式：1.长度为5,2.前四位为大写字母或者小写字母，3.最后一位是数字。
```java
  
package bao;  
  
import java.util.Random;  
  
public class aa {  
    public static void main(String[] args) {  
        char[] chs = new char[52];  
        for (int i = 0; i < chs.length; i++) {  
            if(i<=25){  
                chs[i] = (char) (97 + i);  
            }  
            else{  
                chs[i] = (char)(65+i-26);  
            }  
        }  
        String result =" ";  
        Random r = new Random();  
        for (int i = 0; i < 4; i++) {  
            int rand = r.nextInt(chs.length);  
            result = result + chs[rand];  
        }  
        int rand = r.nextInt(10);  
        result = result + rand;  
        System.out.println(result);  
    }  
}
```
#### 一个满足条件后再进行下一个循环
```java
for(int i=0;i<point.length;){  
    int score =sc.nextInt();  
    if(score>=0 && score>=100){  
        point[i]=score;  
        i++;  
    }  
}
```
