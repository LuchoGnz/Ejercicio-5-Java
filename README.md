# Ejercicio-5-Java
package ejercicios;

import java.util.ArrayList;
import java.util.Iterator;
import java.util.Scanner;

public class Principal {

	public static void main(String[] args) {
		
    		
		 			System.out.println("Ejercicio N°5: ");
	 	Scanner ingresoemp = new Scanner(System.in);
	 	Empleado[] Empleados = new Empleado [20];
	 	System.out.print("Ingrese sueldo base: ");
	 	int sueldoBase = Integer.parseInt(ingresoemp.nextLine());
	 	
	 
	 	for (int i = 0; i < 2; i++) {
	 		
	 			int sueldo = 0;
	 			Empleado emp = new Empleado();
	 			emp.setSueldobase(Double.parseDouble(ingresoemp.nextLine()));
	 			System.out.print("Ingrese apellido empleado: ");
	 			emp.setApellido(ingresoemp.nextLine());		
	 			
	 			System.out.print("Ingrese nombre empleado: ");
	 			emp.setNombre(ingresoemp.nextLine());
	 			
	 			System.out.print("Ingrese DNI empleado: ");
	 			emp.setDni(Integer.parseInt(ingresoemp.nextLine()));
	 			
	 			System.out.print("Ingrese email empleado: ");
	 			emp.setEmail(ingresoemp.nextLine());
	 			
	 			System.out.print("Ingrese tipo de empleado Administrativo o Vendedor (A / V): ");
	 			emp.tipoe= ingresoemp.nextLine();
	 			if (emp.tipoe.equals("A")) {
	 				System.out.println("Ingrese la cantidad de horas normales trabajadas en el mes: ");
	 				emp.hsMes = (Double.parseDouble(ingresoemp.nextLine()));
	 				System.out.println("Ingrese la cantidad de horas extras trabajadas en el mes: ");
	 				emp.hsExtra = (Double.parseDouble(ingresoemp.nextLine()));
	 		} 
	 			else {
	 			int com = 0, ventas = 0;
	 			System.out.println("Ingrese el porcentaje de comisión: ");
	 			com = (Integer.parseInt(ingresoemp.nextLine()));
	 			System.out.println("Ingrese la cantidad de ventas realizadas: ");
	 			ventas = (Integer.parseInt(ingresoemp.nextLine()));
	 			}
	 			emp.calcularSueldo();
	 			//Empleados[i] = "Empleado N°" + (i+1) +":"+ " Apellido:" + emp.apellido + " Nombre:" + emp.nombre + " DNI:" + emp.dni + " E-					     mail:" + emp.email + " Sueldo:" + emp.getSueldo();
	 			Empleados[i]= emp;
	 	}
	 	
	 	for (int i = 0; i < 2; i++) {
	 		System.out.println(Empleados[i]);;
	 	}
	 
	 	ingresoemp.close();
	 	
	 	
	}
}
		 	
		}
	}

  
CLASE EMPLEADO.  

package ejercicios;

import java.util.Scanner;

public class Empleado {

int dni;
String nombre;
String apellido;
String email;
String tipoe;
double sueldobase;

public String getTipoe() {
	return tipoe;
}
public void setTipoe(String tipoe) {
	this.tipoe = tipoe;
}
public double getSueldobase() {
	return sueldobase;
}
public void setSueldobase(double sueldobase) {
	this.sueldobase = sueldobase;
}
public int getDni() {
	return dni;
}
public String getNombre() {
	return nombre;
}
public String getApellido() {
	return apellido;
}
public String getEmail() {
	return email;
}
public void setDni(int dni) {
	this.dni = dni;
}
public void setNombre(String nombre) {
	this.nombre = nombre;
}
public void setApellido(String apellido) {
	this.apellido = apellido;
}
public void setEmail(String email) {
	this.email = email;
}

public String getInfo() {
	String Info="Empleado: ";
	System.out.println("Nombre: ");
	Info+=this.getNombre();
	System.out.println(" Apellido: ");
	Info+=this.getApellido();
	System.out.println(" DNI: ");
	Info+=this.getDni();
	System.out.println(" E-mail:");
	Info+=this.getEmail();
	return Info;
	
}

public String toString() {
	return "\nEmpleado [DNI=" + dni + ", Nombre=" + nombre + ", Apellido" + apellido + ", e-mail=" + email;
}


public double calcularSueldo (){
	
	double sueldo = 0;
	double hsMes = 0, hsExtra = 0;
		if (this.tipoe.equals("A")) { 
		sueldo = this.sueldoBase * ((hsExtra * 1.5)+hsMes) / hsMes;
		return sueldo;
} 
	else {
	sueldo = sueldoBase + (com * ventas /100);
	return sueldo;
	}
	    
	
}

}
	
