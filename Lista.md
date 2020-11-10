# Grupo1_Listas
Primer Seminario de Est. de bases de datos UAPA
using System;
using System.Collections.Generic;
using System.Net.Http.Headers;

namespace lista_numeros
{
    class Program
    {
        static void Main(string[] args)
        {
            //Insertar un elemento en una lista vacía (Lohanny León)

            List<int> listadenumeros = new List<int>();

            listadenumeros.Add(5);
            listadenumeros.Add(8);

            //Insertar un elemento en la primera posición de una lista(Lohanny León)
            listadenumeros.Insert(0, 2);
            listadenumeros.Insert(1, 4);

            foreach (int lista_numeros in listadenumeros)
            {
                Console.WriteLine(lista_numeros);

            }

            

            //Insertar un elemento en la última posición de una lista(Danny González)
            int posicion = listadenumeros.Count;
            posicion -= 1;
            Console.WriteLine("Introduce la nueva ultima posicion");
            listadenumeros[posicion] = int.Parse(Console.ReadLine());

            Console.WriteLine("\nLista actualizada\n");
            for (int x = 0; x < listadenumeros.Count; x++) Console.WriteLine(listadenumeros[x]);

            //Insertar un elemento a continuación de uno dado(Danny González)
            Console.WriteLine("\nIntroduce la posición y el nuevo elemento para agregar, separados por un enter");
            listadenumeros.Insert(int.Parse(Console.ReadLine()), int.Parse(Console.ReadLine()));//Insertar un elemento por teclado

            Console.WriteLine("\nLista actualizada\n");
            for (int x = 0; x < listadenumeros.Count; x++) Console.WriteLine(listadenumeros[x]);
            
            
               //Buscar elementos en una lista (Angela Guzman)
            Console.WriteLine("Introduce el elemnto que deseas buscar en la lista");
            bool Busqueda = listadenumeros.Contains(int.Parse(Console.ReadLine()));
            if (Busqueda == true) Console.WriteLine("El elemento se encuentra en la lista");
            else Console.WriteLine("El elemento no se encuentra en la lista actual");
            Console.ReadKey();

            //Eliminar el primer elemento de una lista(Angela Guzman)

            listadenumeros.RemoveAt(0);
            Console.Clear();//Limpiar la pantalla
            Console.WriteLine("\nNueva lista actualizada");
            foreach (int lista_numeros in listadenumeros)
            {
                Console.WriteLine(lista_numeros);

            }

            Console.ReadKey();
        }
        
    }
}
