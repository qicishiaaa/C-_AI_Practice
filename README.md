#顺序·分支·循环结构

##题单一：顺序结构

###1.小写字母转化为大写字母
```cpp
#include<iostream>
using namespace std;
int main(){
    char c;
    cin>>c;
    cout<<char(c-32);
    return 0;
}


###2.浮点数反转
```cpp
#include <iostream>
#include <string>
#include <cmath>
#include <algorithm>
using namespace std;
int main() {
    double num;
    cin >> num;
    int integer_part = static_cast<int>(num);
    double decimal_part = num - integer_part;
    bool is_one_decimal = (fabs(decimal_part * 10 - round(decimal_part * 10)) < 1e-6) && (decimal_part != 0);
    if (integer_part <= 100 || integer_part >= 1000 || !is_one_decimal) {
        cout << "请输入大于100且小于1000的一位小数的浮点数" << endl;
        return 0;
    }
    int dec = static_cast<int>(round(decimal_part * 10));
    string int_str = to_string(integer_part);
    reverse(int_str.begin(), int_str.end());
    cout << dec << "." << int_str << endl;
    return 0;
}


###3.上学迟到
```cpp
#include <iostream>
#include <cmath>
#include <iomanip>
using namespace std;
int main() {
    int s, v;
    cin >> s >> v;
    int t_walk = (s + v - 1) / v;  
    int total_time = t_walk + 10;
    int school_time = 8 * 60;
    int start_time = school_time - total_time;
    if (start_time < 0) {
        start_time += 24 * 60;  
    }
    int hour = start_time / 60;
    int minute = start_time % 60;
    cout << setw(2) << setfill('0') << hour << ":"
         << setw(2) << setfill('0') << minute << endl;
    return 0;
}

##题单二：分支结构

###1.isbn码
```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
char s[14];
cin>>s;
char a[14];
int m=0;
a[1]=s[0]-'0';
a[2]=s[2]-'0';
a[3]=s[3]-'0';
a[4]=s[4]-'0';
a[5]=s[6]-'0';
a[6]=s[7]-'0';
a[7]=s[8]-'0';
a[8]=s[9]-'0';
a[9]=s[10]-'0';
 if(s[12]=='X')
      a[10]=10;
   else
   a[10]=s[12]-'0';
for(int i=1;i<=9;i++)
    {
       m+=a[i]*i;
     }
    m%=11;
 if(m==a[10])
    cout<<"Right";
 else   
    {for(int i=0;i<12;i++)
        cout<<s[i];
    if(m==10)
       cout<<'X';
    else
       cout<<m;
    }
return 0;
}


##2.ABC
```cpp
#include <bits/stdc++.h>
using namespace std;
int p[3];
int main()
{
    int a,b,c;
    cin>>a>>b>>c;
    char i,j,k;
    cin>>i>>j>>k;
    p[0]=min(a,min(b,c));
    p[2]=max(a,max(b,c));//处理最大和最小的数
    int x=max(a,b),y=max(a,c),z=max(b,c);
    if(x==y) p[1]=z;
    if(x==z) p[1]=y;
    if(y==z) p[1]=x//处理中间的数
    cout<<p[i-65]<<" "<<p[j-65]<<" "<<p[k-65]<<endl;
    return 0;
}

###3.不高兴的津津
```cpp
#include <bits/stdc++.h>
using namespace std;
int main(){
	int max=8,maxi=0;
	for(int i=1;i<=7;i++){
		int t1,t2;//津津在学校上课的时间和妈妈安排她上课的时间
		cin>>t1>>t2;
		if(max<t1+t2){
			max=t1+t2;
			maxi=i;
		}
	}
	cout<<maxi;
	return 0;
}
