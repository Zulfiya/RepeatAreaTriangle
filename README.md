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
        //������ ������
        private float a;
        private float b;
        private float c;
        private float perimeter;
        private double gipotenuza;
        public float area;

        //�����������
        public Triangle() { }
        public Triangle(float a,float b,float c)
        {

            this.a = a;
            this.b = b;
            this.c = c;
            
        }

        //����� ��� ������� ��������� ������������
        public void  CalculatePerimeter(float a, float b, float c)
        {
            perimeter = (a + b + c) / 2;

            Console.WriteLine(" ��������  ����� : {0}", perimeter);

        }

        //����� ��� ������� ���������� �������������� ������������
        public void CalculateGipotinuza(double a, double b)
        {
            double gipa = Math.Pow(a, 2);
            double gipb = Math.Pow(b, 2);
            double gipc = gipa + gipb;
            gipotenuza = Math.Sqrt(gipc);

            Console.WriteLine("���� ����������� ������������� �� c ������ ���� ����� : {0}", gipotenuza);

        }

        //����� ��� ������� ������� �������������� ������������ �� ������� ������
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

            Console.Write("������� �������� ������  a:");
            string aa;
            aa = Console.ReadLine();

            Console.Write("������� �������� ������ b:");
            string bb;
            bb = Console.ReadLine();

           
            double aaa = double.Parse(aa);
            double bbb = double.Parse(bb);
          
            c1.CalculateGipotinuza(aaa,bbb);

          Console.Write("������� �������� ���������� c:");
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

