using System;
using System.Collections.Generic;

namespace BudgetManager
{
    class Program
    {
        static void Main(string[] args)
        {
            decimal totalIncome = 0;
            decimal totalExpenses = 0;

            while (true)
            {
                Console.WriteLine("Выберите действие:");
                Console.WriteLine("1. Добавить доход");
                Console.WriteLine("2. Добавить расход");
                Console.WriteLine("3. Показать баланс");
                Console.WriteLine("4. Выход");
                Console.Write("Ваш выбор: ");
                
                string choice = Console.ReadLine();

                switch (choice)
                {
                    case "1":
                        Console.Write("Введите сумму дохода: ");
                        if (decimal.TryParse(Console.ReadLine(), out decimal income))
                        {
                            totalIncome += income;
                            Console.WriteLine($"Доход добавлен: {income}.");
                        }
                        else
                        {
                            Console.WriteLine("Некорректное значение.");
                        }
                        break;

                    case "2":
                        Console.Write("Введите сумму расхода: ");
                        if (decimal.TryParse(Console.ReadLine(), out decimal expense))
                        {
                            totalExpenses += expense;
                            Console.WriteLine($"Расход добавлен: {expense}.");
                        }
                        else
                        {
                            Console.WriteLine("Некорректное значение.");
                        }
                        break;

                    case "3":
                        decimal balance = totalIncome - totalExpenses;
                        Console.WriteLine($"Ваш баланс: {balance} (Доходы: {totalIncome}, Расходы: {totalExpenses}).");
                        break;

                    case "4":
                        Console.WriteLine("Выход из программы.");
                        return;

                    default:
                        Console.WriteLine("Некорректный выбор. Пожалуйста, выберите снова.");
                        break;
                }

                Console.WriteLine(); // Пустая строка для лучшего восприятия
            }
        }
    }
}
