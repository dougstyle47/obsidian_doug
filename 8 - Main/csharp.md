```c#

string nome = "Bob";
int number = 3;
float number2 = 34.4F;

Console.WriteLine("Hello, " + nome + " You have " + number + " messages in your inbox. The temperature is " + number2 + " celsius");

```

```c#
int firstNumber = 12;
int secondNumber = 7;

Console.WriteLine(firstNumber + secondNumber);

  
string firstName = "Bob";
int widgetsSold = 7;
Console.WriteLine(firstName + " sold " + widgetsSold + " widgets.");
Console.WriteLine(firstName + " sold " + widgetsSold + 7 + " widgets.");
Console.WriteLine(firstName + " sold " + (widgetsSold + 7) + " widgets.");
```

Operações Matemáticas
```c#
int sum = 7 + 5;
int difference = 7 - 5;
int product = 7 * 5;
int quotient = 7 / 5;

Console.WriteLine("Sum: " + sum);
Console.WriteLine("Difference: " + difference);
Console.WriteLine("Product: " + product);
Console.WriteLine("Quotient: " + quotient);
```

```c#
decimal decimalQuotient = 7.0m / 5;
Console.WriteLine($"Decimal quotient: {decimalQuotient}");
```

```c#
int first = 7;
int second = 5;
decimal quotient = (decimal)first / (decimal)second;
Console.WriteLine(quotient);
```

Resto da divisão por inteiros
```c#
Console.WriteLine($"Modulus of 200 / 5 : {200 % 5}"); 
Console.WriteLine($"Modulus of 7 / 5 : {7 % 5}");
```

Ordem de Operação
```c#
int value1 = 3 + 4 * 5;
int value2 = (3 + 4) * 5;

Console.WriteLine(value1);
Console.WriteLine(value2);
```

Incremento e Decremento
```c#
int value = 0; // value is now 0.
value = value + 5; // value is now 5.
Console.WriteLine(value);
value += 5; // value is now 10.
Console.WriteLine(value);
```

```c#
int value = 1;

value = value + 1;
Console.WriteLine("First increment: " + value);

value += 1;
Console.WriteLine("Second increment: " + value);

value++;
Console.WriteLine("Third increment: " + value);

value = value - 1;
Console.WriteLine("First decrement: " + value);

value -= 1;
Console.WriteLine("Second decrement: " + value);

value--;
Console.WriteLine("Third decrement: " + value);
```

```c#
int value = 1;

value++;
Console.WriteLine("First: " + value);
Console.WriteLine($"Second: {value++}");
Console.WriteLine("Third: " + value);
Console.WriteLine("Fourth: " + (++value));
```

Fahrenheit to Celsius
```c#
int fahrenheit = 94;
decimal celsius = (fahrenheit-32) * (5m/9m);

Console.WriteLine(celsius);
```

```c#

```

```c#

```

```c#

```

```c#

```

```c#

```

```c#

```