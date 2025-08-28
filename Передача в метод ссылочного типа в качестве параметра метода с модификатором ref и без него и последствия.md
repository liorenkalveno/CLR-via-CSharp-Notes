## Передача ссылочного типа в метод без модификатора ref и последствия

```
class Person
{
    public string Name { get; set; }        
}

public class Program
{
    static void ReplacePerson(Person p)
    {
        p = new Person { Name = "Bob" };
    }

    public static void Main()
    {
        Person person = new Person { Name = "Alice" };
        ReplacePerson(person);

        Console.WriteLine(person.Name); // Alice

        Console.ReadKey();
    }
}
```


## Передача ссылочного типа в метод с модификатором ref и последствия
```
class Person
{
    public string Name { get; set; }        
}

public class Program
{
    static void ReplacePerson(ref Person p)
    {
        p = new Person { Name = "Bob" };
    }

    public static void Main()
    {
        Person person = new Person { Name = "Alice" };
        ReplacePerson(ref person);

        Console.WriteLine(person.Name); // Bob

        Console.ReadKey();
    }
}
```