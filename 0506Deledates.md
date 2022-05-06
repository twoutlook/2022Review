# Rainer Stropek 採用了幾乎最簡的方式來演示 C# Delegates
- https://www.youtube.com/watch?v=nhJ63BnlP5I
## dnSpy , dn is dotnet



```
using System;

namespace DelegatesAndLambdasNet5
{
    class Program
    {
        static void Main(string[] args)
        {
          

            CalculateAndPrint(12, 34, Add);
            CalculateAndPrint(12, 34, Subtract);

        }
        delegate int MathOp(int x, int y);
        delegate float MathOpV2(float x, float y);
        static void CalculateAndPrint(int x, int y, MathOp f)
        {
            var result=f(x, y); 
            Console.WriteLine(result);
        }
        static int Add(int x, int y)
        {

            return x + y;
        }
        static float AddV2(float x, float y)
        {

            return x + y;
        }
        static int Subtract(int a, int b)
        {

            return a - b;
        }
    }
}


```


## 官網中文機器翻譯
- Introduction to delegates and events in C#
- https://docs.microsoft.com/zh-tw/dotnet/csharp/delegates-overview
- C 中的委派和事件簡介#
