1、平方根的格式化     
知识点：平方根计算 1  pow(a,0.5)[可以计算负数，结果为复数]      
          2  a**b           
例题：   
获得用户输入的一个整数a，计算a的平方根，保留小数点后3位，并打印输出。‪‬‪‬‪‬‪‬‪‬‮‬‭‬‪‬‪‬‪‬‪‬‪‬‪‬‮‬‫‬‮‬‪‬‪‬‪‬‪‬‪‬‮‬‪‬‫‬‪‬‪‬‪‬‪‬‪‬‮‬‫‬‪‬‪‬‪‬‪‬‪‬‪‬‮‬‪‬‫‬  

输出结果采用宽度30个字符、右对齐输出、多余字符采用加号(+)填充。‪‬‪‬‪‬‪‬‪‬‮‬‭‬‪‬‪‬‪‬‪‬‪‬‪‬‮‬‫‬‮‬‪‬‪‬‪‬‪‬‪‬‮‬‪‬‫‬‪‬‪‬‪‬‪‬‪‬‮‬‫‬‪‬‪‬‪‬‪‬‪‬‪‬‮‬‪‬‫‬  

如果结果超过30个字符，则以结果宽度为准。      

#我的答案：  
```py
a=eval(input())
    print("{0:+>30.3f}".format(pow(a,0.5)))
```
#运行结果：  
1、10    
+++++++++++++++++++++++++3.162   
2、-10  
++++++++++++++++++0.000+3.162j   
#点评分析：  
这是一个简单题，重点在于理解格式化输出的方法。   

注意：如果平凡根后产生一个复数，由于复数的实部和虚部都是浮点数，.3f可以将实部和虚部分别取三位小数。   

1.1、凯撒密码（ 栅栏密码 ） 
```py
plaincode=input("请输入明文：")
for p in plaincode:
    if ord("a")<=ord(p)<=ord("z"):
        print(chr(ord('a')+(ord(p)-ord('a')+3)%26),end="")  #end="",是不想让【循环】输出换行。因为print自带换行。
    else:                                                 # %26,mod26是因为＋3后可能超出范围，通过这个操作限定范围
        print(p,end="")
```
1.2、随机密码生成   
描述   
补充编程模板中代码，完成如下功能：‪‬‪‬‪‬‪‬‪‬‮‬‭‬‪‬‪‬‪‬‪‬‪‬‪‬‮‬‫‬‮‬‪‬‪‬‪‬‪‬‪‬‮‬‪‬‫‬‪‬‪‬‪‬‪‬‪‬‮‬‫‬‪‬‪‬‪‬‪‬‪‬‪‬‮‬‪‬‫‬    

以整数17为随机数种子，获取用户输入整数N为长度，产生3个长度为N位的密码，密码的每位是一个数字。每个密码单独一行输出。‪‬‪‬‪‬‪‬‪‬‮‬‭‬‪‬‪‬‪‬‪‬‪‬‪‬‮‬‫‬‮‬‪‬‪‬‪‬‪‬‪‬‮‬‪‬‫‬‪‬‪‬‪‬‪‬‪‬‮‬‫‬‪‬‪‬‪‬‪‬‪‬‪‬‮‬‪‬‫‬    

产生密码采用random.randint()函数。  
#建议答案：
```py
import random

def mima(length):
    a=10**(length-1)
    b=10**length - 1
    return "{}".format(random.randint(a,b))  #居然可以return这个东西

length=eval(input())
random.seed(17)
for i in range(3):
    print(mima(length))
```
2、字符串分段组合   
知识点：str.split("xxxxx"),返回一个 列表 ，由str中被 xxxxx 分隔的部分组成   
例题：   
获得输入的一个字符串s，以字符减号(-)分割s，将其中首尾两段用加号(+)组合后输出。    
#我的答案：   
```py
s=input()
for i in range(0,99991):
    if(s[i]=="-"):
        a=s[0:i]
        break
for j in range(1,99999):
    if(s[-j]=="-"):
        b=s[(-j)+1:-1]
        break
print("{}+{}{}".format(a,b,s[-1]))
```
#运行结果：   
1-2-3-4   
1+4   
#建议答案：   
```py
s=input()
ls=s.split("-")
print("{}+{}".format(ls[0],ls[-1]))
```
#运行结果：   
1-2-3-4   
1+4   

3、四位玫瑰数   
描述‪‬‪‬‪‬‪‬‪‬‮‬‭‬‪‬‪‬‪‬‪‬‪‬‪‬‮‬‫‬‮‬‪‬‪‬‪‬‪‬‪‬‮‬‪‬‫‬‪‬‪‬‪‬‪‬‪‬‮‬‫‬‪‬‪‬‪‬‪‬‪‬‪‬‮‬‪‬‫‬：   

四位玫瑰数是4位数的自幂数。自幂数是指一个 n 位数，它的每个位上的数字的 n 次幂之和等于它本身。‪‬‪‬‪‬‪‬‪‬‮‬‭‬‪‬‪‬‪‬‪‬‪‬‪‬‮‬‫‬‮‬‪‬‪‬‪‬‪‬‪‬‮‬‪‬‫‬‪‬‪‬‪‬‪‬‪‬‮‬‫‬‪‬‪‬‪‬‪‬‪‬‪‬‮‬‪‬‫‬     

例如：当n为3时，有1^3 + 5^3 + 3^3 = 153，153即是n为3时的一个自幂数，3位数的自幂数被称为水仙花数。‪‬‪‬‪‬‪‬‪‬‮‬‭‬‪‬‪‬‪‬‪‬‪‬‪‬‮‬‫‬‮‬‪‬‪‬‪‬‪‬‪‬‮‬‪‬‫‬‪‬‪‬‪‬‪‬‪‬‮‬‫‬‪‬‪‬‪‬‪‬‪‬‪‬‮‬‪‬‫‬   

请输出所有4位数的四位玫瑰数，按照从小到大顺序，每个数字一行。   ‪‬‪‬‪‬‪‬‪‬‮‬‭‬‪‬‪‬‪‬‪‬‪‬‪‬‮‬‫‬‮‬‪‬‪‬‪‬‪‬‪‬‮‬‪‬‫‬‪‬‪‬‪‬‪‬‪‬‮‬‫‬‪‬‪‬‪‬‪‬‪‬‪‬‮‬‪‬‫‬


#我的答案：   
```py
for i in range(1000,10000):
    a=i//1000
    b=(i%1000)//100
    c=((i%1000)%100)//10
    d=((i%1000)%100)%10
    if(a**4+b**4+c**4+d**4==i):
        print("{}\n".format(i))
```
#建议答案：   
```py
s = ""
for i in range(1000, 10000):
    t = str(i)
    if pow(eval(t[0]),4) + pow(eval(t[1]),4) + pow(eval(t[2]),4) + pow(eval(t[3]),4) == i :
        print(i)
```
#分析解释   
1、print()本身就带有换行了   
2、eval（）评估函数，居然可以把数当作字符串处理，及其简单的得到这个数的个位、十位、百位、等等             

4、100以内素数之和   
描述   
求100以内所有素数之和并输出。‪‬‪‬   ‪‬‪‬‪‬‮‬‭‬‪‬‪‬‪‬‪‬‪‬‪‬‮‬‫‬‮‬‪‬‪‬‪‬‪‬‪‬‮‬‪‬‫‬‪‬‪‬‪‬‪‬‪‬‮‬‫‬‪‬‪‬‪‬‪‬‪‬‪‬‮‬‪‬‫‬
素数指从大于1，且仅能被1和自己整除的整数。   ‪‬‪‬‪‬‪‬‪‬‮‬‭‬‪‬‪‬‪‬‪‬‪‬‪‬‮‬‫‬‮‬‪‬‪‬‪‬‪‬‪‬‮‬‪‬‫‬‪‬‪‬‪‬‪‬‪‬‮‬‫‬‪‬‪‬‪‬‪‬‪‬‪‬‮‬‪‬‫‬

提示：可以逐一判断100以内每个数是否为素数，然后求和。   

#我的答案：   
在cpp里，是两个for循环，然后判断（2，n）之后，n是否还等于i   
#建议答案：   
```py
#Prime
def is_prime(n):
    for i in range(2,n):
        if n%i == 0:
            return False
    return True
sum = 0
for i in range(2,100):
    if is_prime(i):
        sum += i
print(sum)
```
5、连续素数（质数）计算    
知识点1：str字符串不能单独赋值，和cpp不一样，所以直接输出   
知识点2：python在使用变量前不需要定义，用的时候，进行什么样的操作，就可以看出是什么变量类型 
知识点3：与cpp不同的是：python中 for一般是遍历，while一般限定循环次数。
描述   
补充编程模板中代码，完成如下功能：   ‪‬‪‬‪‬‪‬‪‬‮‬‭‬‪‬‪‬‪‬‪‬‪‬‪‬‮‬‫‬‮‬‪‬‪‬‪‬‪‬‪‬‮‬‪‬‫‬‪‬‪‬‪‬‪‬‪‬‮‬‫‬‪‬‪‬‪‬‪‬‪‬‪‬‮‬‪‬‫‬

获得用户输入数字N，计算并输出从N开始的5个质数，单行输出，质数间用逗号,分割。‪‬‪‬‪‬‪‬‪‬‮‬‭‬‪‬‪‬‪‬‪‬‪‬‪‬‮‬‫‬‮‬‪‬‪‬‪‬‪‬‪‬‮‬‪‬‫‬‪‬‪‬‪‬‪‬‪‬‮‬‫‬‪‬‪‬‪‬‪‬‪‬‪‬‮‬‪‬‫‬   

注意：需要考虑用户输入的数字N可能是浮点数，应对输入取整数；最后一个输出后不用逗号。   
#我的答案：  
#建议答案：   
```py
def sushu(m): #判断素数的函数
    for i in range(2,m):
        if m%i == 0:
            return False
    return True  #注意缩进，是for循环完了还不满足，才return True

n=eval(input())
n_=int(n)+1   #把浮点数换成整数
count=5       #限定输出个数
while count>0: # count =5,4,3,2,1都可以循环，不就是循环5次嘛🐎
    if sushu(n_):
        if count>1: #这个东西是为了前4次输出有结尾的逗号，
            print(n_,end=",")
        else:
            print(n_,end="")
        count-=1  #注意缩进，不管啥，只要 if sushu（）成立[是素数]，都要把计数器减1
    n_+=1     #注意缩进，不管啥，每次搞完都要把 n_加1，方能遍历 【遍历】
```

6、七段数码管turtle绘制    
知识点：   
1 函数定义与编写   
2 return   
3 局部变量和全局变量    
4 参数传递问题  
#建议答案：   
```py
import turtle
def drawgap():      #画空白函数
    turtle.penup()
    turtle.fd(5)
def drawline(line): #画线条函数
    drawgap()
    turtle.pendown() if line else turtle.penup
    turtle.fd(20)
    drawgap()
    turtle.right(90)
def drawdigit(digit):  #画一个数码函数
    drawline(1) if digit in [2,3,4,5,6,8,9] else drawline(0)
    drawline(1) if digit in [0,1,3,4,5,6,7,8,9] else drawline(0)
    drawline(1) if digit in [0,2,3,5,6,8,9] else drawline(0)
    drawline(1) if digit in [0,2,6,8] else drawline(0)
    turtle.left(90)
    drawline(1) if digit in [0,4,5,6,8,9] else drawline(0)
    drawline(1) if digit in [0,2,3,5,6,7,8,9] else drawline(0)
    drawline(1) if digit in [0,1,2,3,4,7,8,9] else drawline(0)
    turtle.right(180)
    turtle.fd(10)
def drawdate(date):   #需要的日期函数
    for p in date:
        drawdigit(eval(p))
def main():           #主函数
    turtle.setup(800,250,200,300)
    turtle.pensize(5)
    turtle.penup()
    turtle.fd(-150)
    drawdate("20200117")
    turtle.hideturtle()
    turtle.done()
main()
```

7、汉诺塔问题    
知识点：函数递归调用     
三个部分    
1 函数＋分支(if ->3 else ->2)    
2链条   
3基例    
#建议答案
```py
count=0
def han(n,A,C,B):  #四个参数采用位置传递，代表的含义分别为：搬运圆盘编号，圆盘起始位置，圆盘目标位置，过渡位置
    global count
    if n==1:
        print("{}:{}->{}".format(1,A,C))
        count+=1
    else:          #递归链条表示：先把上面n-1个搬到过渡位置，剩的那个最大的放到目标位置，再把那n-1个放到目标位置
        han(n-1,A,B,C)
        print("{}:{}->{}".format(n,A,C))
        count+=1
        han(n-1,B,C,A)
print(han(3,"A","C","B"))  #以三个圆盘为例
print(count)
```
#输出结果：  
```
1:A->C
2:A->B
1:C->B
3:A->C
1:B->A
2:B->C
1:A->C
7
```
8、基本统计值计算    
总和、平均数、中位数、方差
```py
def getnum():
    ls=[]
    nums=input("请输入数字：")
    while nums !='':
        ls.append(eval(nums))
        nums=input("请输入数字：")
    return ls
def pingjun(ls):
    sum=0.0
    for p in ls:
        sum+=p
    return sum/len(ls)

def fangcha(ls,ave):
    sum=0.0
    for p in ls:
        sum+=(p-ave)**2
    return sum

def mid(ls):
    sorted(ls)
    size=len(ls)
    if size%2==0:
        med=(ls[size//2-1]+ls[size//2])/2
    else:
        med=ls[size//2]
    return med

n=getnum()

print("平均数：{}\n方差{}\n中位数{}\n".format(pingjun(n),fangcha(n,pingjun(n)),mid(n)))

```
