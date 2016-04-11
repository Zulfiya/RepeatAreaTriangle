# RepeatAreaTriangle
Repeat area triangle

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace AreaTtriangle
{
    
    class Triangle

    {
        //Данные класса
        private float a;
        private float b;
        private float c;
        private float perimeter;
        private double gipotenuza;
        public float area;

        //Конструктор
        public Triangle() { }
        public Triangle(float a,float b,float c)
        {

            this.a = a;
            this.b = b;
            this.c = c;
            
        }

        //Метод для расчета периметра треугольника
        public void  CalculatePerimeter(float a, float b, float c)
        {
            perimeter = (a + b + c) / 2;

            Console.WriteLine(" Периметр  равен : {0}", perimeter);

        }

        //Метод для расчета гипотенузы прямоугольного треугольника
        public void CalculateGipotinuza(double a, double b)
        {
            double gipa = Math.Pow(a, 2);
            double gipb = Math.Pow(b, 2);
            double gipc = gipa + gipb;
            gipotenuza = Math.Sqrt(gipc);

            Console.WriteLine("Если треугольник прямоугольный то c должно быть равно : {0}", gipotenuza);

        }

        //Метод для расчета площади прямоугольного треугольника по формуле Герона
        public void  CalculateArea(float a, float b)
        {
            area = (perimeter-a)*(perimeter-b);
        }

        public virtual void DisplayStats()
        {

            Console.WriteLine("Area: {0}", area );

        }

    }
    class Program
    {

        static void Main(string[] args)
        {
            Triangle c1;
            c1 = new Triangle();

            Console.Write("Введите значение катета  a:");
            string aa;
            aa = Console.ReadLine();

            Console.Write("Введите значение катета b:");
            string bb;
            bb = Console.ReadLine();

           
            double aaa = double.Parse(aa);
            double bbb = double.Parse(bb);
          
            c1.CalculateGipotinuza(aaa,bbb);

          Console.Write("Введите значение гипотенузы c:");
            string cc;
    
                
            cc = Console.ReadLine();

            double ccc = double.Parse(cc);



            float sta;
            float stb;
            float stc;
            sta = float.Parse(aa);
            stb = float.Parse(bb);
            stc = float.Parse(cc);

            
            
            c1 = new Triangle(sta, stb, stc);
            c1.CalculatePerimeter(sta, stb, stc);
            c1.CalculateArea(sta, stb);
            c1.DisplayStats();
            Console.ReadLine();
            
         



        }
    }
}

