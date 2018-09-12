import os 
import sys

###文件夹名字 test
dirname = 'test'
###文件的名字是 text.txt

filename = 'test.txt'
###判断当前路径是否存在 test 文件夹， 如果没有则创建该文件夹

if not os.path.exists(dirname):
	os.mkdir(dirname)
###指定文件的路径, 这没有创建文件

filepath = os.path.join(dirname, filename)
###在指定路径创建并打开 test.txt 文件， 并写入内容

with open(filepath, 'w', encoding='utf8') as fp:
	fp.write('这是一个测试文件!')
###打印文件夹test的绝对路径

print(os.path.abspath(dirname))
###这个会打印当前运行文件路径和filepath 的拼接字符串

print(os.path.abspath(filepath))
###这个会返回当前运行文件的系统路径

print(sys.path[0])
###这种方法可以给当前运行文件添加识别路径，方便调用模块（模块路径 /home/module/func.py）

sys.path.append(/home/module/)
###添加了以上一句就可以直接调用模块 func(这样就不会导致引用错误)

import func
