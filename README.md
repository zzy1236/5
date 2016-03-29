# 5 #include <iostream>
  2 #include <cstring>
  3 #include <fstream>
  4 using namespace std;
  5 
  6 struct WORD {                           /* 创建一个结构体 */
  7     int    count;
  8     char    s;
  9     void    exchange( Word &word )  /* 交换单词 */
 10     {
 11         string    tStr    = word.Str;
 12         int    tCount    = word.Count;
 13         word.Str    = Str;
 14         word.Count    = Count;
 15         Str        = tStr;
 16         Count        = tCount;
 17     }
 18 };
 19 } w[100];
 20 
 21 bool isword( char a[] ) /* 判断是否是一个单词 */
 22 {
 23     int i = 0;
 24     for ( i = 0; a[i] != '\0'; i++ )
 25         if ( (a[i] >= 'a' && a[i] <= 'z') || (a[i] >= '0' && a[i] <= '9') )
 26             return(true);
 27         else
 28             return(false);
 29 }
 30 
 31 
 32 int judge( char b[], int n )                            /* 判断该单词是否出现过 */
 33 {
 34     if ( n > 0 )
 35         for ( int i = 0; i < n; i++ )
 36         {
 37             if ( !strcmp( b, &w[i].s ) )    /* 出现 */
 38             {
 39                 w[i].count++;
 40                 return(-1);
 41             }
 42         }
 43 }
 44 
 45 
 46 void SortWordDown( Word * words, int size )  /* 降序排序 */
 47 {
 48     for ( int i = 0; i < size; i++ )
 49     {
 50         for ( int j = 0; j < size - 1; j++ )
 51         {
 52             if ( words[j].Count < words[j + 1].Count )
 53             {
 54                 words[j].exchange( words[j + 1] );
 55             }
 56         }
 57     }
 58 }
 59 
 60 
 61 int main( void )
 62 {
 63     char result[500];
 64 
 65     char *ptr;
 66     ifstream file( "c://A_Tale_of_Two_Cities.txt" ); /* 读取 */
 67     if ( !file )
 68     {
 69         cout << "不能打开文件";
 70     }
 71     while ( !file.eof() )
 72     {
 73         file.getline( result, 500 );
 74     }
 75     file.close();
 76     int j = 0; /* 大写转小写 */
 77     while ( result[j] != '/0' && result[j + 1] != '/0' )
 78     {
 79         if ( result[j] >= 'A' && result[j] <= 'Z' )
 80         {
 81             result[j] = result[j] - 'A' + 'a';
 82             j++;
 83         }
 84     }
 85     cout << result;
 86     char *sep = " ";
 87 
 88     int i = 0;
 89     ptr = strtok( result, " " );            /* 利用strtok函数来分割result字符串中的单词 */
 90     while ( ptr != NULL )
 91     {
 92         if ( isword( p ) != false )
 93         {
 94             if ( judge( p, n ) != false )
 95             {
 96                 w[n].s = *p;    /* 赋值给数组 */
 97                 n++;
 98             }
 99         }
100         ptr = strtok( NULL, " " );
101     }
102     int t = 0;
103     ofstream outfile;                       /* 输出文件到result1 */
104     outfile.open( "Result1.txt" )
105     SortWordDown( w, count );
106     while ( w[t].s )                        /* 输出统计结果 */
107     {
108         if ( strlen( w[t].s ) >= 4 )
109         {
110             outfile << w[t].s << "：" << w[t].count << '\n';
111             t++;
112         }
113     }
114     return(0);
115 }
复制代码
