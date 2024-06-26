#### Условие задачи:

![Condition](./src/Aleksa_and_Stack.png)

Обязательная ссылка на [CodeForces](https://codeforces.com/contest/1878/problem/B?locale=ru)

#### Решение:

```
internal class Program
{
    static void Main(string[] args)
    {
        int sets = Convert.ToInt32(Console.ReadLine());
        for (int i = 0; i < sets; i++) 
        {
            int size = Convert.ToInt32(Console.ReadLine());
            int[] arr = new int[size];
            arr[0] = 5;
            arr[1] = 8;

            for (int j = 2; j < size; j++) 
                arr[j] = ReturnInt(arr[j - 1], arr[j - 2]);

            for (int j = 0; j < size - 1; j++)
                Console.Write(arr[j] + " ");

            Console.WriteLine(arr[size - 1]);
        }
    }
 
    static int ReturnInt (int pre, int prepre)
    {
        int current = pre + 1 ;
        while ((3 * current) / (pre + prepre) == 0)
            current++;
        
        return current;
    }
}
```