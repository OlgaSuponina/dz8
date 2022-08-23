//Задача 54: Задайте двумерный массив. Напишите программу,
 которая упорядочит по убыванию элементы
 каждой строки двумерного массива.

Console.WriteLine("Введите кол-во строк: ");
int n = Convert.ToInt32(Console.ReadLine());
Console.WriteLine("Введите кол-во столбцев: ");
int m = Convert.ToInt32(Console.ReadLine());

int[,] arr = new int[n, m];
            Console.WriteLine("");
            for (int i = 0; i < arr.GetLength(0); i++)
            {
                for (int j = 0; j < arr.GetLength(1); j++)
                {
                    arr[i, j] = new Random().Next(1, 99);
                    Console.Write(arr[i, j] + " \t");
                }
                Console.WriteLine();
            }
            Console.WriteLine("");

            for (int i = 0; i < arr.GetLength(0); i++) 
            {
                for (int j = arr.GetLength(1) - 1; j > 0; j--)
                {

                    for (int k = 0; k < j; k++)
                    {
                        if (arr[i, k] > arr[i, k + 1])
                        {
                            int temp = arr[i, k];
                            arr[i, k] = arr[i, k + 1];
                            arr[i, k + 1] = temp;
                        }
                    }
                }
                Console.WriteLine();
            }

            for (int i = 0; i < arr.GetLength(0); i++)
            {
                for (int j = 0; j < arr.GetLength(1); j++)
                {
                    Console.Write("{0,3}", arr[i, j]);
                }
                Console.WriteLine();
            }





//Задача 56: Задайте прямоугольный двумерный массив. 
Напишите программу, 
которая будет находить строку с наименьшей суммой элементов.

Console.Write("Введите количество строк в матрице: ");
int n = Convert.ToInt32(Console.ReadLine());
Console.Write("Введите количество столбцов в матрице: ");
int m = Convert.ToInt32(Console.ReadLine());
Random rnd = new Random();
int[,] matrix = new int[n, m];
for (int i = 0; i < n; i++)
            for (int j = 0; j < m; j++)
                matrix[i, j] = rnd.Next(1, 10 );
 
        for (int i = 0; i < n; i++, Console.WriteLine())
            for (int j = 0; j < m; j++)
                Console.Write(matrix[i, j] + "\t");
          int minRowSum = int.MaxValue, indexMinRow = 0;
 
         for (int i = 0; i < n; i++)
         {
            int rowSum = 0;
              for (int j = 0; j < m; j++)
                rowSum += matrix[i, j];
                
            if (rowSum < minRowSum)
            {
                minRowSum = rowSum;
                indexMinRow = i;
            }
         }
    Console.WriteLine($"\n{indexMinRow+1} - строкa с наименьшей суммой ({minRowSum}) элементов ");
  




//Задача 58: Задайте две матрицы.
 Напишите программу, которая будет находить произведение двух матриц.



Console.Write("Введите количество строк в матрице: ");
int n = Convert.ToInt32(Console.ReadLine());
Console.Write("Введите количество столбцов в матрице: ");
int m = Convert.ToInt32(Console.ReadLine());
int[,] MatrixOne = new int[n, m];
int[,] MatrixTwo = new int[n, m];
Console.WriteLine("Начальная матрица 1: ");
NewMatrix(MatrixOne);
Console.WriteLine();
Console.WriteLine("Начальная матрица 2: ");
NewMatrix(MatrixTwo);
Console.WriteLine("Конечная матрица: ");
ProzMatrixs(MatrixOne, MatrixTwo);

void NewMatrix(int[,] matrix)
{
for (int i = 0; i < matrix.GetLength(0); i++)
            for (int j = 0; j < matrix.GetLength(1); j++)

                matrix[i, j] = new Random().Next(1, 10 );
 
        for (int i = 0; i < n; i++, Console.WriteLine())
            for (int j = 0; j < m; j++)
                Console.Write(matrix[i, j] + "\t");
}
void ProzMatrixs(int[,] MatrixOne, int[,] MatrixTwo)    
{
     int[,] ResultMatrix = new int[MatrixOne.GetLength(0), MatrixOne.GetLength(1)];
     for (int i = 0; i < MatrixOne.GetLength(0); i++) 
     {
         for (int j = 0; j < MatrixOne.GetLength(1); j++) 
         {
         ResultMatrix[i, j] = MatrixOne[i, j] * MatrixTwo[i, j];
         Console.Write(ResultMatrix[i, j] + " ");
         }
         Console.WriteLine();
     }

}            




//Задача 60. Сформируйте трёхмерный массив из неповторяющихся 
двузначных чисел.
Напишите программу, которая будет построчно выводить массив, 
добавляя индексы каждого элемента.

массив размером 2 x 2 x 2  



Console.Clear();
Console.WriteLine($"\nВведите размер массива X x Y x Z:");
int x = InputNumbers("Введите X: ");
int y = InputNumbers("Введите Y: ");
int z = InputNumbers("Введите Z: ");
Console.WriteLine("");

int[,,] array3D = new int[x, y, z];
WriteArray(array3D);

int InputNumbers(string input)
{
  Console.Write(input);
  int output = Convert.ToInt32(Console.ReadLine());
  return output;
}

void WriteArray (int[,,] array3D)
{
  for (int i = 0; i < array3D.GetLength(0); i++)
  {
    for (int j = 0; j < array3D.GetLength(1); j++)
    {
      Console.Write($"X({i}) Y({j}) ");
      for (int k = 0; k < array3D.GetLength(2); k++)
      {
        Console.Write( $"Z({k})={array3D[i,j,k]}; ");
      }
      Console.WriteLine();
    }
    Console.WriteLine();
  }
}
 



//Задача 62. Заполните спирально массив 4 на 4.


void NewMatrix(int[,] matrix)
{
    int temp = 1; i = 0; j = 0;
    while (temp <= matrix.GetLength(0) * matrix.GetLength(1))
    {     
          matrix[i, j] = temp;
          temp++;
          if(i <= j + 1 && i + j < matrix.GetLength(1) - 1)
             j++;
          else if(i < j + 1 && i + j <= matrix.GetLength(1) - 1)
             i++; 
          else if(i >= j && i + j > matrix.GetLength(1) - 1)
             j--;  
          else
             i --;
    }      
    for (i = 0; i < matrix.GetLength(0); i++) 
    {
         for j = 0; j < matrix.GetLength(1); j++)
         Console.Write(matrix[i, j] + "\t");
         Console.WriteLine();
    }    
}



Console.Write("Введите количество строк в матрице: ");
int x = Convert.ToInt32(Console.ReadLine());
Console.Write("Введите количество столбцов в матрице: ");
int y = Convert.ToInt32(Console.ReadLine());
int[,] MatrixOne = new int[x, y];
NewMatrix(MatrixOne);
                        