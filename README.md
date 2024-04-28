using System;

public class Persona
{
    private string nombre;
    private int edad;
    private string direccion;
    private string correoElectronico;

    public Persona(string nombre, int edad, string direccion, string correoElectronico)
    {
        this.nombre = nombre;
        this.edad = edad;
        this.direccion = direccion;
        this.correoElectronico = correoElectronico;
    }

    // Getters y Setters para los campos (propiedades)
    public string Nombre { get => nombre; set => nombre = value; }
    public int Edad { get => edad; set => edad = value; }
    public string Direccion { get => direccion; set => direccion = value; }
    public string CorreoElectronico { get => correoElectronico; set => correoElectronico = value; }
}

public class EmailService
{
    public void EnviarCorreoElectronico(string destinatario, string mensaje)
    {
        // Lógica para enviar correo electrónico
        Console.WriteLine($"Enviando correo electrónico a {destinatario}: {mensaje}");
    }
}

public class PrinterService
{
    public void ImprimirDatos(Persona persona)
    {
        Console.WriteLine($"Nombre: {persona.Nombre}");
        Console.WriteLine($"Edad: {persona.Edad}");
        Console.WriteLine($"Dirección: {persona.Direccion}");
        Console.WriteLine($"Correo electrónico: {persona.CorreoElectronico}");
    }
}

class Program
{
    static void Main()
    {
        Persona persona = new Persona("Jhon", 19, "Calle duarte", "jhonbaez858@gmail.com");

        PrinterService printerService = new PrinterService();
        printerService.ImprimirDatos(persona);

        EmailService emailService = new EmailService();
        emailService.EnviarCorreoElectronico(persona.CorreoElectronico, "¡Hola! Este es un mensaje de prueba.");
    }
}
