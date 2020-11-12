# Grupo1_Listas
Primer Seminario de Est. de bases de datos UAPA
using System;
namespace ListasGenericas
{
    
    class Program
    {
        
        static void Main(string[] args)
        {

            Lista NuevaLista = new Lista();
            //elementos de la lista
            NuevaLista.Agregar("Primer elemento");
            NuevaLista.Agregar("Segundo elemento");
            NuevaLista.Agregar("Tercer elemento");
            NuevaLista.Agregar("Cuarto elemento"); 
            NuevaLista.Agregar("Quinto elemento");
            NuevaLista.Agregar("Sexto elemento");
            
            NuevaLista.Posicion(3, "Introducido");//Metodo para introducir elementos en una posicion dada
           
            NuevaLista.Imprimir();//Metodo para imprimir la lista



        }
    }
     
    class nodo
    {
        public string dato;
        public nodo siguiente;

        public  string Dato
        {
            get { return dato; }
            set { dato = value; }
        }

        public nodo Siguiente
        {
            get { return siguiente; }
            set { siguiente = value; }
        }
    }
    
    
    class Lista
    {
        private nodo Primero= new nodo();//Primera posicion
        private nodo Ultimo = new nodo();//Ultima posicion

        public Lista()//Constructor de la clase lista
        {
            Primero = null;
            Ultimo = null;
        }

        public void Agregar(string entrada)//Metodo para insertar elementos a la ultima posicion de la lista
        {
            nodo Nuevo = new nodo();
            Nuevo.Dato = entrada;
            if (Primero == null)
            {
                Primero = Nuevo;
                Primero.Siguiente = null;
                Ultimo = Nuevo;
            }
            else
            {

                Ultimo.Siguiente = Nuevo;
                Nuevo.Siguiente = null;
                Ultimo = Nuevo;
            }

        }
        

        public void Imprimir()//Metodo para imprimir la lista
        {
            nodo Actual = new nodo();
            Actual = Primero;
            if (Primero != null)
            {
                while (Actual != null)
                {
                    Console.WriteLine(Actual.Dato);
                    Actual = Actual.Siguiente;
                }
            }
            
        }


        public void Posicion(int posicion, string entrada)//Introduce un elemento por posicion dada
        {
            nodo auxiliar = new nodo();//Nuevo nodo
            auxiliar.Dato = entrada;
            auxiliar.Siguiente = null;
            if (Primero == null)//Si la lista esta vacia introduce un elemento
            {
                auxiliar = Primero;
            }
            else
            {
                nodo puntero;//Marcara la posicion de la lista
                puntero = Primero;
                if (posicion == 1)//En caso que se desee introducir en la primera posicion
                {
                    Primero = auxiliar;
                    auxiliar.Siguiente = puntero;
                }
                else
                {
                    for(int i=1; i<posicion-1; i++)
                    {
                        puntero = puntero.Siguiente;
                        if (puntero.Siguiente == null) break;//Final de la lista 
                    }
                    //Abrir nuevo espacio en la lista
                    nodo punterosig;//(puntero siguiente) ayudara a marcar las posiciones
                    punterosig = puntero.Siguiente;//Toma la posicion del puntero principal
                    puntero.Siguiente = auxiliar;//Puntero principal apunta al nuevo nodo
                    auxiliar.Siguiente = punterosig;//Nuevo nodo apunta al puntero siguiente
                }
            }
        }
    }
}
