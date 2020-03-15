# Computer
The operation of two numbers.

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

namespace computer_1
{
    class Program
    {
        static void Main(string[] args)
        {
            int x, y;
            char z;
            try
            {
                Console.WriteLine("请输入第一个数字");
                x = int.Parse(Console.ReadLine());
                Console.WriteLine("请输入第二个数字");
                y = int.Parse(Console.ReadLine());
                Console.WriteLine("请输入符号");
                z = (char)Console.Read();
                switch (z)
                {
                    case '+':
                        Console.WriteLine("{0}{1}{2}={3}", x, z, y, x + y);
                        break;
                    case '-':
                        Console.WriteLine("{0}{1}{2}={3}", x, z, y, x - y);
                        break;
                    case '*':
                        Console.WriteLine("{0}{1}{2}={3}", x, z, y, x * y);
                        break;
                    case '/':
                        try
                        {
                            Console.WriteLine("{0}{1}{2}={3}", x, z, y, x / y);

                        }
                        catch
                        {
                            Console.WriteLine("计算错误，除法第二个数字不能为0");
                        }
                        break;
                    default:
                        Console.WriteLine("输入错误，请正确输入");
                        break;
                }
            }
            catch
            {
                Console.WriteLine("输入错误，请正确输入");
            }
        }
    }
}
