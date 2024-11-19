# Inheritance

using System;
public class Base
{
// Public fields (to allow direct access and modification)
public int i, j;
// Method to set values
public void Set(int a, int b)
{
i = a;
j = b;
}
// Method to display the values of i and j
public void Show()
{
Console.WriteLine(i + " " + j);
}
}
// Derived class that inherits from Base
public class Derived : Base
{
// Public field specific to the derived class
public int k;
// Constructor to initialize the value of k
public Derived(int x)
{
k = x;
}
// Method to display the value of k
public void ShowK()
 {
Console.WriteLine(k);

 }
}

2.
using System;
public class Base
{
public int publicValue = 10;
protected int protectedValue = 20;
private int privateValue = 30;
public void Display()
{
Console.WriteLine("Base public value: " + publicValue);
Console.WriteLine("Base protected value: " + protectedValue);
Console.WriteLine("Base private value: " + privateValue); // Accessible here
}
}
public class Derived : Base
{
public void Show()
{
Console.WriteLine("Derived public value: " + publicValue); // Accessible
Console.WriteLine("Derived protected value: " + protectedValue); // Accessible
// Console.WriteLine("Derived private value: " + privateValue); // Not accessible, Show error
}
}
class Program
{
static void Main(string[] args)
{
Derived obj = new Derived();
obj.Show();
}
}

3.Example of Multiple Inheritance in C# Using Interfaces:

using System;

// Printer interface

public interface IPrinter

{

void Print(string document);

}

// Scanner interface

public interface IScanner

{

void Scan(string document);

}

// Copier interface

public interface ICopier

{

void Copy(string document);

}

// Multi-function device implementing all interfaces

public class MultiFunctionDevice : IPrinter, IScanner, ICopier

{

public void Print(string document)

{

Console.WriteLine("Printing document: " + document);

}

public void Scan(string document)

{

Console.WriteLine("Scanning document: " + document);

}

public void Copy(string document)

{

Console.WriteLine("Copying document: " + document);

}

}

// Simple Printer-only device

public class PrinterOnlyDevice : IPrinter

{

public void Print(string document)

{

Console.WriteLine("Printing document: " + document);

}

}

class Program

{

static void Main()

{

// Multi-function device that can print, scan, and copy

MultiFunctionDevice mfd = new MultiFunctionDevice();

Console.WriteLine("Using MultiFunctionDevice:");

mfd.Print("ProjectReport.pdf");

mfd.Scan("ProjectReport.pdf");

mfd.Copy("ProjectReport.pdf");

// Printer-only device

PrinterOnlyDevice printer = new PrinterOnlyDevice();

Console.WriteLine("\nUsing PrinterOnlyDevice:");

printer.Print("Resume.pdf");

}

}
