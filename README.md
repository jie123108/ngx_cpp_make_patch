nginx C++ ֧�ֲ��� 
===================================  
  nginx C++ ֧�֡�nginxĬ�ϲ�֧��C++�ļ�����Ҫ�޸���auto/make��������޸ĵ�patch�ϴ�������
	��Ҳ����ͨ���޸�./configure���Makefile��֧��C++����ÿ��./configure����Ҫ�ظ��޸ģ�����ֱ���޸�auto/make�ǱȽϺõķ�ʽ


���Թ��İ汾  
-----------------------------------  
	nginx-1.0.15
	nginx-1.2.9
	nginx-1.4.5
	nginx-1.5.10


Ӧ�ò���
----------------------------------- 
	cd nginx-1.4.5
	patch -p1 < ../nginx-cpp_make.patch 
 	Ȼ��Ϳ�����nginxʹ��.cpp��β��C++�ļ��ˡ�

### ˵����

��patch��Ҫ�޸���auto/make�ļ������뵽�жϣ����ļ���׺��.cppʱ��ʹ��g++���룬����ʹ��g++���ӡ�

### ��ʾ��
	���Ҫ��.c�ļ��а���cpp��.h������cpp��.h��ʹ������Ĵ��룺
	
	#ifdef   __cplusplus
	extern "C"{
	#endif
	
	#�м���ĺ�������
	
	
	#ifdef   __cplusplus
	}
	#endif
	
	
	���Ҫ��.cpp�а���C��ͷ�ļ���
	extern "C" {
	#include <C��ͷ�ļ�.h>
	}
	
	#include "C++��ͷ�ļ�.h"

