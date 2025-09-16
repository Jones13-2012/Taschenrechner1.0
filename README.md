using System;

class Taschenrechner
{
    static void Main()
    {
        Console.WriteLine("Einfacher Taschenrechner (+, -, *, /)");
        while (true)
        {
            Console.Write("Gib die Rechnung ein (z.B. 4 + 5) oder 'ende' zum Beenden: ");
            string eingabe = Console.ReadLine();

            if (eingabe.Trim().ToLower() == "ende")
            {
                Console.WriteLine("Taschenrechner wird beendet.");
                break;
            }

            string[] teile = eingabe.Split(' ');
            if (teile.Length != 3)
            {
                Console.WriteLine("Bitte gib die Rechnung im Format 'Zahl1 Operator Zahl2' ein.");
                continue;
            }

            double zahl1, zahl2;
            if (!double.TryParse(teile[0], out zahl1) || !double.TryParse(teile[2], out zahl2))
            {
                Console.WriteLine("Ungültige Zahlen. Bitte erneut versuchen.");
                continue;
            }

            string op = teile[1];
            double ergebnis = 0;
            bool gueltig = true;

            switch (op)
            {
                case "+":
                    ergebnis = zahl1 + zahl2;
                    break;
                case "-":
                    ergebnis = zahl1 - zahl2;
                    break;
                case "*":
                    ergebnis = zahl1 * zahl2;
                    break;
                case "/":
                    if (zahl2 == 0)
                    {
                        Console.WriteLine("Fehler: Division durch 0 nicht möglich.");
                        gueltig = false;
                    }
                    else
                    {
                        ergebnis = zahl1 / zahl2;
                    }
                    break;
                default:
                    Console.WriteLine("Unbekannter Operator. Bitte +, -, * oder / verwenden.");
                    gueltig = false;
                    break;
            }

            if (gueltig)
            {
                Console.WriteLine($"Ergebnis: {ergebnis}");
            }
        }
    }
}
