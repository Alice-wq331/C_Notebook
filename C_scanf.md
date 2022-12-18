### 进一步理解scanf函数的使用
#### 扫描一整行的输入（扫描输入直到换行）
```C
# include <stdio.h>
# include <stdlib.h>

int main(){
    char c[100];
    scanf("%[^\n]",c);
return 0;
}
```
问题：
   当连续使用scanf扫描多行输入，从第二个scanf()开始会自动新开启一行，则用%[^\n]将扫描不到想要的该行输入，因为开始就停止。
解决： 
如同scanf("")中加空格会skip用户输入的空格，scanf()中加"\n"会跳过用户的换行。我们可以用 
```C
scanf("%[上一行结果]\n %[^\n]",&[第一个variable],[string variable]")
```
来skip两行输入之间的换行
