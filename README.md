# C-Sharp-Projeleri-Daire-Cizme

Kullanıcıdan alınan yarıçapa göre console'a Daire çizen uygulamayı yazınız.

    using System;

    class Program {
      static void Main(string[] args)  {
        double r;
        double thickness = 0.4;

        do  {
          Console.Write("yaricapi gir; ");
          if (!double.TryParse(Console.ReadLine(), out r) || r <= 0)  {
            Console.WriteLine("Pozitif sayi olmak zorunda");
          }
        }

        while (r <= 0);

        Console.WriteLine();
        double rIn = r - thickness;
        double rOut = r + thickness;

        for (double y = r; y >= -r; --y)  {
          for (double x = -r; x < rOut; x += 0.5)  {
            double value = x * x + y * y;

            if (value >= rIn * rIn && value <= rOut * rOut)
              Console.Write("*");
            else
                Console.Write(" ");
          }

          Console.WriteLine();

        }

        Console.ReadKey();

      }

    }
