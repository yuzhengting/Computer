# Computer
The operation of two strings.

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
        
            string one, two;
            char sign;
            int count_one = 0;
            int count_two = 0;
            Console.WriteLine("请输入第一个字符串");
            one = Console.ReadLine();
            Console.WriteLine("请输入第二个字符串");
            two = Console.ReadLine();
            Console.WriteLine("请输入符号");
            sign = (char)Console.Read();
            for (int i = 0; i < one.Length; i++)
                if (one[i] >= 48 && one[i] <= 57)
                    count_one++;
            for (int i = 0; i < two.Length; i++)
                if (two[i] >= 48 && two[i] <= 57)
                    count_two++;
            if (count_one == one.Length && count_two == two.Length)
                Int_Computer(int.Parse(one), int.Parse(two), sign);
            else if (count_one == 0 && count_two == 0)
                String_Computer(one, two, sign);
            else
                Console.WriteLine("输入错误，请重新运行程序");
            
        }
        public static void Int_Computer(int one, int two, char sign)
        {
            switch (sign)
            {
                case '+':
                    Console.WriteLine("{0}{1}{2}={3}", one, sign, two, one + two);
                    break;
                case '-':
                    Console.WriteLine("{0}{1}{2}={3}", one, sign, two, one - two);
                    break;
                case '*':
                    Console.WriteLine("{0}{1}{2}={3}", one, sign, two, one * two);
                    break;
                case '/':
                    try
                    {
                        Console.WriteLine("{0}{1}{2}={3}", one, sign, two, one / two);

                    }
                    catch
                    {
                        Console.WriteLine("计算错误，除法第二个数字不能为0，请重新运行程序");
                    }
                    break;
                default:
                    Console.WriteLine("符号错误，请重新运行程序");
                    break;
            }
        }
        public static void String_Computer(string one,string two,char sign)
        {
            string three = "";
            int count = 0;
            bool flag = true;
            switch (sign)
            {
                case '+':
                    three = one + two;
                    Console.WriteLine("{0}{1}{2}={3}", one, sign, two, three);
                    break;
                case '-':
                    for (int i = 0; i < one.Length; )
                    {
                        if (one[i] == two[0] && flag == true)
                        {
                            if (one.Length - i < two.Length)
                            {
                                flag = false;
                                continue;
                            }
                            count++;
                            for (int j = 1; j < two.Length; j++)
                                if (one[j + i] == two[j])
                                    count++;
                        }
                        if (count == two.Length)
                        {
                            i += two.Length;
                            flag = false;
                        }
                        else
                        {
                            three += one[i];
                            i++;
                        }
                        count = 0;
                    }
                    if (three.Length == 0)
                        Console.WriteLine("{0}{1}{2}=空", one, sign, two);
                    else if (three.Length == one.Length)
                        Console.WriteLine("这俩字符串不能做减法运算");
                    else
                        Console.WriteLine("{0}{1}{2}={3}", one, sign, two, three);
                    break;
                default:
                    Console.WriteLine("符号错误，请重新运行程序");
                    break;
            }
        }
    }
}
