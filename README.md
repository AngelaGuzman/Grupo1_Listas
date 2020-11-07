# Grupo1_Listas
Primer Seminario de Est. de bases de datos UAPA



Eliminar un elemento dada la posicion 


using System;
using System.Collections.Generic; //Debes agregar esta linea si no la tienes a tu using tal cual la ves aqui.

class MainClass {
  public static void Main (string[] args) {
    
    //Todos los elementos de la lista
    List<int> lista = new List<int> {1,2,3,4,5,6,7,8,9,10};

    //Mensaje para que ingreses la posicion a eliminar.
    Console.WriteLine("Ingrese la posicion de la lista que desea eliminar");

      //Variable para guardar la posicion ingresada.
      int posicionElementoDado = Convert.ToInt32(
      Console.ReadLine());

      //Espacio en blanco para hacer un salto de linea y despegar el numero ingresado del resultado.
      Console.WriteLine();

    //Remueve el elemento si esta en la lista.
     lista.RemoveAt(posicionElementoDado);

    //Bucle o ciclo para recorrer la lista y mostrar todos los elementos que no fueron eliminados.
    foreach(int ls in lista)
    {
      //Imprime todos los elementos que no fueron eliminados
      Console.WriteLine(ls);
    }

    //Permite que la consola permanezca abierta luego de mostrar el resultado
    Console.ReadKey();
  }  
}







Eliminar un elemento dado 


using System;
using System.Collections.Generic; //Debes agregar esta linea si no la tienes a tu using tal cual la ves aqui.

class MainClass {
  public static void Main (string[] args) {
    
    //Todos los elementos de la lista
    List<int> lista = new List<int> {1,2,3,4,5,6,7,8,9,10};

    //Mensaje para que ingreses el numero a eliminar.
    Console.WriteLine("Ingrese el elemento de la lista que desea eliminar");

      //Variable para guardar el numero ingresado.
      int ElementoDado = Convert.ToInt32(
      Console.ReadLine());

      //Espacio en blanco para hacer un salto de linea y despegar el numero ingresado del resultado.
      Console.WriteLine();

  //Condicion para saber si el elemento que se ingreso se encuentra en la lista para luego eliminarlo.
  if(lista.Contains(ElementoDado))
  {
    //Remueve el elemento si esta en la lista.
     lista.Remove(ElementoDado);

    //Bucle o ciclo para recorrer la lista y mostrar todos los elementos que no fueron eliminados.
    foreach(int ls in lista)
    {
      //Imprime todos los elementos que no fueron eliminados
      Console.WriteLine(ls);
    }
  }
  else{
          //Muestra mensaje en caso de digitar un numero que no este en la lista.
          Console.WriteLine("No se puede eliminar ese elemento porque no existe en la lista");
  }

    //Permite que la consola permanezca abierta luego de mostrar el resultado
    Console.ReadKey();
  }  
  
  
  
  
  
  
  
  
  
  
  
