# calculator3000
Just a calculator
using System;

class Calculator
{
    static void Main()
    {
        Console.WriteLine("Простой калькулятор на C#");
        
        Console.Write("Введите первое число: ");
        double num1 = Convert.ToDouble(Console.ReadLine());
        
        Console.Write("Введите оператор (+, -, *, /): ");
        char op = Console.ReadLine()[0];
        
        Console.Write("Введите второе число: ");
        double num2 = Convert.ToDouble(Console.ReadLine());
        
        double result = 0;
        bool validOperation = true;
        
        switch (op)
        {
            case '+':
                result = num1 + num2;
                break;
            case '-':
                result = num1 - num2;
                break;
            case '*':
                result = num1 * num2;
                break;
            case '/':
                if (num2 != 0)
                    result = num1 / num2;
                else
                {
                    Console.WriteLine("Ошибка: Деление на ноль невозможно!");
                    validOperation = false;
                }
                break;
            default:
                Console.WriteLine("Ошибка: Неверный оператор!");
                validOperation = false;
                break;
        }

        if (validOperation)
            Console.WriteLine($"Результат: {result}");
        
        Console.WriteLine("Нажмите любую клавишу для выхода...");
        Console.ReadKey();
    }
}
