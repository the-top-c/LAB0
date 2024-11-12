# LAB0
This is my first assignment,and it is about building a computer with storage.

#准备
fh=['+','-','*','/']                                            #存储计算符号
p=['0','1','2','3','4','5','6','7','8','9']                     #存储数字
s={}                                                            #存储计算式子
x=0                                                             #记录计算次数
d=False                                                         #判断数字

#正式开始计算
while True:                                                     #开始无限循环
    a=input()                                                   #输入第一个字符
    if a in fh:                                                 #判断a是否为计算字符
        b=int(input())                                          #输入计算符号前面的数字
        c=int(input())                                          #输入计算符号后面的数字
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
            if c==0:                                            #判断除数是否为0
                print('除数不能为0')
            else:
                d='{:.2f}'.format(b/c)                          #保留两位小数
                print(d)
                s[x]='{0}/{1}={2}'.format(b,c,d)
        x=x+1                                                   #每计算一次记录次数
        print(s)                                                #输出每次计算的式子
    else:
        for i in a:
            if i in p:                                          #判断a是否含有其他字符（如-）
                d=True
                break                                           #出现数字，终止循环
        if d==True:
            if int(a)>=0:                                       #判断数字的正负
                print(s[int(a)])
            else:
                e=len(s)+int(a)                                 #转换负数为正常的次序数
                if e>=0:                                        #判断转换后的数字是否为正数
                    print(s[e])
                else:
                    print('输入个数不足')                        #判断输入的数字转换后的次序是否超出已计算的次数
            d=False                                             #恢复原始参数，方便进行下一次计算
        else:
            print('请输入数字或运算符号')                         #若输入的a既不是计算符号也不是数字，开始下一次输入并进行提示
