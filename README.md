nginx C++ 支持补丁 
===================================  
  nginx C++ 支持。nginx默认不支持C++文件，需要修改下auto/make。下面把修改的patch上传上来。
	你也可以通过修改./configure后的Makefile来支持C++，但每次./configure后都需要重复修改，所以直接修改auto/make是比较好的方式


测试过的版本  
-----------------------------------  
	nginx-1.0.15
	nginx-1.2.9
	nginx-1.4.5
	nginx-1.5.10


应用补丁
----------------------------------- 
	cd nginx-1.4.5
	patch -p1 < ../nginx-cpp_make.patch 
 	然后就可以在nginx使用.cpp结尾的C++文件了。

### 说明：

该patch主要修改了auto/make文件，加入到判断，当文件后缀是.cpp时，使用g++编译，并且使用g++链接。

### 提示：
	如果要在.c文件中包含cpp的.h，请在cpp的.h中使用下面的代码：
	
	#ifdef   __cplusplus
	extern "C"{
	#endif
	
	#中间你的函数声明
	
	
	#ifdef   __cplusplus
	}
	#endif
	
	
	如果要在.cpp中包含C的头文件：
	extern "C" {
	#include <C的头文件.h>
	}
	
	#include "C++的头文件.h"

