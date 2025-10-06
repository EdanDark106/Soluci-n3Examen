// Clase base Profesional
abstract class Profesional {
    protected String nombre;
    protected String especialidad;
    protected int añosExperiencia;

    public Profesional(String nombre, String especialidad, int añosExperiencia) {
        this.nombre = nombre;
        this.especialidad = especialidad;
        this.añosExperiencia = añosExperiencia;
    }

    public int getAñosExperiencia() {
        return añosExperiencia;
    }

    // Método para comparar años de experiencia
    public int compararAtributos(Profesional otro) {
        return Integer.compare(this.añosExperiencia, otro.añosExperiencia);
    }

    public void mostrarInfo() {
        System.out.println("Nombre: " + nombre + ", Especialidad: " + especialidad + ", Años de experiencia: " + añosExperiencia);
    }
}

// Clase Nutricionista
class Nutricionista extends Profesional {
    private String numeroLicencia;
    private String enfoqueNutricional;
    private int pacientes;

    public Nutricionista(String nombre, String especialidad, int añosExperiencia,
                         String numeroLicencia, String enfoqueNutricional, int pacientes) {
        super(nombre, especialidad, añosExperiencia);
        this.numeroLicencia = numeroLicencia;
        this.enfoqueNutricional = enfoqueNutricional;
        this.pacientes = pacientes;
    }

    public void mostrarInfo() {
        super.mostrarInfo();
        System.out.println("Número de Licencia: " + numeroLicencia + ", Enfoque: " + enfoqueNutricional + ", Pacientes: " + pacientes);
    }
}

// Clase Abogado
class Abogado extends Profesional {
    private String numeroColegiado;
    private String especialidadLegal;
    private int casosActivos;

    public Abogado(String nombre, String especialidad, int añosExperiencia,
                   String numeroColegiado, String especialidadLegal, int casosActivos) {
        super(nombre, especialidad, añosExperiencia);
        this.numeroColegiado = numeroColegiado;
        this.especialidadLegal = especialidadLegal;
        this.casosActivos = casosActivos;
    }

    public void mostrarInfo() {
        super.mostrarInfo();
        System.out.println("Número de Colegiado: " + numeroColegiado + ", Especialidad Legal: " + especialidadLegal + ", Casos Activos: " + casosActivos);
    }
}

// Clase Informatico
class Informatico extends Profesional {
    private String certificaciones;
    private String lenguajeProgramacion;
    private int proyectos;

    public Informatico(String nombre, String especialidad, int añosExperiencia,
                       String certificaciones, String lenguajeProgramacion, int proyectos) {
        super(nombre, especialidad, añosExperiencia);
        this.certificaciones = certificaciones;
        this.lenguajeProgramacion = lenguajeProgramacion;
        this.proyectos = proyectos;
    }

    public void mostrarInfo() {
        super.mostrarInfo();
        System.out.println("Certificaciones: " + certificaciones + ", Lenguaje: " + lenguajeProgramacion + ", Proyectos: " + proyectos);
    }
}

// Clase principal para probar
public class Main {
    public static void main(String[] args) {
        // f) Crear 1 objeto Nutricionista, 2 objetos Abogado y 2 objetos Informatico
        Nutricionista nutri = new Nutricionista("Ana Gomez", "Nutrición Deportiva", 5, "NUT123", "Deporte", 50);
        Abogado abog1 = new Abogado("Carlos Perez", "Derecho Penal", 10, "ABG456", "Penal", 15);
        Abogado abog2 = new Abogado("Maria Lopez", "Derecho Civil", 8, "ABG789", "Civil", 20);
        Informatico info1 = new Informatico("Luis Ruiz", "Desarrollo Web", 7, "Cert1,Cert2", "Java", 10);
        Informatico info2 = new Informatico("Sofia Martinez", "Ciberseguridad", 9, "Cert3", "Python", 12);

        // g) Comparar atributos (años de experiencia)
        System.out.println("\nComparación de años de experiencia:");
        System.out.println("Ana vs Carlos: " + (nutri.compararAtributos(abog1) > 0 ? "Ana tiene más experiencia" : "Carlos tiene más experiencia"));
        System.out.println("Carlos vs Maria: " + (abog1.compararAtributos(abog2) > 0 ? "Carlos tiene más experiencia" : "Maria tiene más experiencia"));

        // h) Hallar los años de estudio (experiencia) de todos los objetos
        System.out.println("\nAños de experiencia de todos los profesionales:");
        nutri.mostrarInfo();
        abog1.mostrarInfo();
        abog2.mostrarInfo();
        info1.mostrarInfo();
        info2.mostrarInfo();
    }
}
