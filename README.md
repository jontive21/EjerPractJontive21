package razasdeperros;
import java.util.ArrayList;
import java.util.Collections;
import java.util.Iterator;
import java.util.Scanner;

public class RazasDePerros {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        ArrayList<String> razasDePerros = new ArrayList<>();
        String respuesta;

        // Bucle para ingresar razas de perros
        do {
            System.out.println("Ingrese una raza de perro:");
            String raza = scanner.nextLine();
            razasDePerros.add(raza);

            System.out.println("¿Desea agregar otra raza de perro? (s/n):");
            respuesta = scanner.nextLine();
        } while (respuesta.equalsIgnoreCase("s"));

        // Mostrar todas las razas de perros ingresadas
        System.out.println("Las razas de perros guardadas son:");
        for (String raza : razasDePerros) {
            System.out.println(raza);
        }

        // Pedir al usuario una raza de perro para eliminar
        System.out.println("Ingrese la raza de perro que desea eliminar:");
        String razaAEliminar = scanner.nextLine();

        // Utilizar Iterator para recorrer y eliminar el perro
        Iterator<String> iterator = razasDePerros.iterator();
        boolean encontrado = false;
        while (iterator.hasNext()) {
            String raza = iterator.next();
            if (raza.equalsIgnoreCase(razaAEliminar)) {
                iterator.remove();
                encontrado = true;
                break;
            }
        }

        // Ordenar la lista
        Collections.sort(razasDePerros);

        // Mostrar la lista ordenada
        if (encontrado) {
            System.out.println("El perro fue eliminado. La lista ordenada de razas es:");
        } else {
            System.out.println("El perro no se encuentra en la lista. La lista ordenada de razas es:");
        }

        for (String raza : razasDePerros) {
            System.out.println(raza);
        }
    }
}
