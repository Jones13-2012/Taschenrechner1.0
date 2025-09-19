// Mathe
float Ergebnis = 0;
string Text = "Ergebnis: ";
try
{
    Console.Write("Gib eine Zahl ein:");
    string Eingabe1 = Console.ReadLine();
    Console.Write("Und jetzt nochmal eine Zahl");
    string Eingabe2 = Console.ReadLine();
    Console.Write("Dann der Operator: ");
    string Operator = Console.ReadLine();
    float Zahl1 = float.Parse(Eingabe1);
    float Zahl2 = float.Parse(Eingabe2);
    
    if (Operator == "+") Ergebnis = Zahl1 + Zahl2;
    if (Operator == "-") Ergebnis = Zahl1 - Zahl2;
    if (Operator == "*") Ergebnis = Zahl1 * Zahl2;
    if (Operator == "/")
        if (Zahl2 != 0) Ergebnis = Zahl1 / Zahl2;
        else Console.WriteLine("Division durch null");
}
catch
{
    Text = " Irgendetwas stimmt nicht!";
}
if (Text == "Ergebnis: ") Text = Text + Ergebnis;
Console.WriteLine(Text);
