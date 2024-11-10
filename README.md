# Exception
using System;

class MyCustomException : Exception
{
    public MyCustomException(string message) : base(message) { }
}

class Program
{
    static void Main()
    {
        try
        {
            Console.WriteLine("Enter a positive number:");
            int number = int.Parse(Console.ReadLine());

            if (number <= 0)
            {
                throw new MyCustomException("The number must be positive!");
            }
            else
            {
                Console.WriteLine("You entered a positive number: " + number);
            }
        }
        catch (MyCustomException ex)
        {
            Console.WriteLine("Caught a custom exception: " + ex.Message);
        }
    }
}
