第一章 程序设计基本方法
第二章 Python程序实例解析
第三章 基本数据类型
第四章 程序的控制结构
#4.2 统计不同字符个数
First attempt:
a,b,c,d=0,0,0,0
s=input()
for p in s:
    if "a"<=p<="z" or "A"<=p<="Z" :
        a+=1
    elif p==" ":
        b+=1
    elif 0<=eval(p)<=9:   #错误出现在这里，其他字符无法进行此步运算
        c+=1
    else:
        d+=1
print("英文字符{}\n空格{}\n数字{}\n其他字符{}\n".format(a,b,c,d))
answer:
a,b,c,d = 0,0,0,0 # a代表英文字符个数 b代表数字个数 c代表空格个数 d代表其他字符个数
strs = input("请随意输入一行字符，包含字母，数字，空格或其他字符：")
for s in strs:
    if ord('a') <= ord(s) <= ord('z') or ord('A') <= ord(s) <= ord('Z'):
        a += 1
    elif ord('0') <= ord(s) <= ord('9'):
        b += 1
    elif ord(' ') == ord(s):
        c += 1
    else:
        d += 1
print("包含字母{0}个，数字{1}个，空格{2}个，其他字符{3}个".format(a,b,c,d)
