import os 
import sys

###�ļ������� test

dirname = 'test'
###�ļ��������� text.txt

filename = 'test.txt'
###�жϵ�ǰ·���Ƿ���� test �ļ��У� ���û���򴴽����ļ���

if not os.path.exists(dirname):
	os.mkdir(dirname)
###ָ���ļ���·��, ��û�д����ļ�

filepath = os.path.join(dirname, filename)
###��ָ��·���������� test.txt �ļ��� ��д������

with open(filepath, 'w', encoding='utf8') as fp:
	fp.write('����һ�������ļ�!')
###��ӡ�ļ���test�ľ���·��

print(os.path.abspath(dirname))
###������ӡ��ǰ�����ļ�·����filepath ��ƴ���ַ���

print(os.path.abspath(filepath))
###����᷵�ص�ǰ�����ļ���ϵͳ·��

print(sys.path[0])
###���ַ������Ը���ǰ�����ļ����ʶ��·�����������ģ�飨ģ��·�� /home/module/func.py��

sys.path.append(/home/module/)
###���������һ��Ϳ���ֱ�ӵ���ģ�� func(�����Ͳ��ᵼ�����ô���)

import func
