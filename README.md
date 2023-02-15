# Ticket-Price-Calculator

import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {

        int distance, ticketType, age;
        double costPerKM = 0.1;
        double totalPrice = 0, finalPrice = 0;
        Scanner scanner = new Scanner(System.in);

        System.out.println("Mesafe giriniz: ");
        distance = scanner.nextInt();

        System.out.println("Yaşınızı giriniz: ");
        age = scanner.nextInt();

        System.out.println("Bilet tipi giriniz: \n 1- Tek Yön \n 2- Gidiş-Dönüş");
        ticketType = scanner.nextInt();

        if(distance < 0 && age < 1 && (ticketType < 1 || ticketType > 2)){
            System.out.println("Hatalı veri girdiniz!");
        }
        else{
            totalPrice = distance * costPerKM;

            if(age < 12){
                totalPrice = totalPrice * 0.5;
            }
            else if(age > 12 && age < 24){
                totalPrice = totalPrice * 0.9;
            }
            else if(age > 65){
                totalPrice = totalPrice * 0.7;
            }
        }

        if(ticketType == 1){
            System.out.println("Total: " + totalPrice);
        }else{
            totalPrice = totalPrice * 2;

            finalPrice = totalPrice * 0.8;

            System.out.println("Total: " + finalPrice);
        }

    }
}
