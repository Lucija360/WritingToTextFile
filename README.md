# WritingToTextFile

Writing stopwatch.ElapsedMilliseconds to text file

## Stopwatch defined outside of the method 

```  public  static void TraceResult(Stopwatch watch)
    {
        var elapsedMs = watch.ElapsedMilliseconds;

        // Displays RunTime value in Milliseconds
        Console.WriteLine($"Run time: {watch.ElapsedMilliseconds} measured in Milliseconds");

        // Displays RunTime value in Minutes
        Console.WriteLine($"Run time:{watch.Elapsed} measured in Minutes");

         string filePath = @"Insert your File Path here ";

        using (var writer = new StreamWriter(filePath, true))
        {
            writer.Write(watch.ElapsedMilliseconds + " " );

        }

        Console.WriteLine("DATA APPENDED TO SPECIFIED TEXT FILE");

    }
```

#### Example Output in your text file

``` 2032 123  23 ```

## Stopwatch defined inside of the method

```var stopwatch = new Stopwatch();
stopwatch.Start();
System.Threading.Thread.Sleep(300);
stopwatch.Stop();

long elapsed = stopwatch.ElapsedMilliseconds;
Console.WriteLine(stopwatch.ElapsedMilliseconds);
Console.WriteLine(elapsed);

//Here are multiple approaches possible
File.WriteAllText(filename, stopwatch.ElapsedMilliseconds.ToString());

using (var writer = new StreamWriter(filename, true))
{
    writer.Write(stopwatch.ElapsedMilliseconds);
};
```

## Stopwatch defined inside of the method(Version 2)

```var stopwatch = new Stopwatch();
stopwatch.Start();
System.Threading.Thread.Sleep(300);
stopwatch.Stop();

long elapsed = stopwatch.ElapsedMilliseconds;
Console.WriteLine(stopwatch.ElapsedMilliseconds);
Console.WriteLine(elapsed);

string filePath = @"Insert your File Path here ";

using (var writer = new StreamWriter(filePath, true))
{
    writer.Write(stopwatch.ElapsedMilliseconds);
};
```

Hopefully this could help you 😃
