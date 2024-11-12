# LAB0
This is my first assignment,and it is about building a computer with storage.

#以Python语言为编
fh=['+','-','*','/']                                        #存储运算符号
p=['0','1','2','3','4','5','6','7','8','9']                 #存储如何判断第一次输入为数字的依据
s={}                                                        #存储运算结果
x=0                                                         #计算过程中的计算次序
d=False                                                     #判断第一个输入是否为负数

#计算机的主体部分
while True:                                                 #进行无限循环，使计算机开始之后可以一直计算下去
    a=input()                                               #输入的第一个字符（计算符号或数字）
    if a in fh:                                             #判断a为计算符号
        b=int(input())                                      #输入计算符号前面的数字
        c=int(input())                                      #输入计算符号后面的数字
        if a=='+':
            print(b+c)
            s[x]='{0}+{1}={2}'.format(b,c,b+c)
        elif a=='-':
            print(b-c)
            s[x]='{0}-{1}={2}'.format(b,c,b-c)
        elif a=='*':
            print(b*c)
            s[x]='{0}*{1}={2}'.format(b,c,b*c)
        elif a=='/':
            if c==0:                                        #判断除数是否为0
                print('除数不能为0')
            else:
                d='{:.2f}'.format(b/c)                      #保留两位小数
                print(d)
                s[x]='{0}/{1}={2}'.format(b,c,d)
        x=x+1
        print(s)                                            #显示存储的结果
    else:
        for i in a:
            if i in p:
                d=True
                break                                       #判断a是否为负数
        if d==True:
            print(s[abs(int(a))])                           #输出存储的列式
            d=False                                         重置判断条件，进行下次判断
        else:
            print('请输入数字或运算符号')
            
