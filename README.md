using System;
using System.Globalization;

class Program
{
    static void Main()
    {
        Console.WriteLine("02_Variables: Types, formatting, parsing");
        Console.WriteLine("----------------------------------------");

        int a = 42;
        double price = 19.95;
        bool isActive = true;
        char symbol = '★';
        string text = "C# practice";

        Console.WriteLine($"int a = {a}, double price = {price}, bool isActive = {isActive}");
        Console.WriteLine($"char symbol = {symbol}, string text = {text}");

        // Formatting
        Console.WriteLine("Price (C culture): " + price.ToString("C", CultureInfo.CurrentCulture));
        Console.WriteLine("Price (en-US): " + price.ToString("C", new CultureInfo("en-US")));

        // Parsing user input
        Console.Write("Enter a number to parse as double: ");
        string input = Console.ReadLine();
        if (double.TryParse(input, NumberStyles.Float, CultureInfo.InvariantCulture, out double parsed))
        {
            Console.WriteLine($"Parsed = {parsed}");
        }
        else
        {
            Console.WriteLine("Could not parse input as a double (use dot for decimal).");
        }
    }
}
