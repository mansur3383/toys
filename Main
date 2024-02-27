package Main;

import Main.Toys.Toy;
import java.io.FileWriter;
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.util.LinkedList;
import java.util.Random;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Path p = Paths.get("gameLog");
        try{
            Files.deleteIfExists(p);
        } catch (IOException e){
            e.printStackTrace();
        }
        Scanner scanner = new Scanner(System.in);
        Toy t = null;
        int count = 0;
        LinkedList<Toy> toys = new LinkedList<>();
        createList(toys);
        System.out.println("Для участия в розыгрыше нажмите 1");
        int roll = scanner.nextInt();
        while (roll != 0) {
            count++;
            if (!toys.isEmpty()) {
                t = getToy(toys);
                if (t == null) {
                    System.out.println("Вы ничего не выиграли");
                    try(FileWriter f = new FileWriter("gameLog", true)){
                        String str = "Шаг: " + count + " выигрыш: null\n";
                        f.write(str);
                    } catch (IOException e){
                        e.printStackTrace();
                    }
                } else {
                    System.out.println(t);
                    try(FileWriter f = new FileWriter("gameLog", true)){
                    String str = "Шаг: " + count + " выигрыш: " + t.getToyName() +" \n";
                    f.write(str);
                    } catch (IOException e){
                        e.printStackTrace();
                    }
                }
                roll = introduction();
            } else {
                System.out.println("В автомате нет игрушек!");
                try(FileWriter f = new FileWriter("gameLog", true)){
                    String str = "Шаг: " + count + " в автомате нет игрушек\n";
                    f.write(str);
                } catch (IOException e){
                    e.printStackTrace();
                }
                roll = 0;
            }

        }
    }

    public static void createList(LinkedList list) {
        for (int i = 0; i < 25; i++) {
            if (i % 13 == 0) {
                list.add(new Toy(i, "PlayStation 5", 0.01));
            }
            if (i % 17 == 0) {
                list.add(new Toy(i, "IPhone 15", 0.01));
            }
            if (i % 3 == 0) {
                list.add(new Toy(i, "Модель Mercedes G55 AMG", 0.1));
            }
            if (i % 5 == 0) {
                list.add(new Toy(i, "Модель Toyota LC 200", 0.1));
            }
            if (i % 2 == 0 && i % 3 != 0 && i % 5 != 0) {
                list.add(new Toy(i, "Модель Lexus IS 250", 0.15));
            }
            if (i % 2 != 0 && i % 3 != 0 && i % 5 != 0) {
                list.add(new Toy(i, "Модель BMW M550i xDrive", 0.15));
            }
        }
    }

    public static Toy getToy(LinkedList<Toy> list) {
        Toy toy = null;
        Random r = new Random();
        int num;
        num = r.nextInt(0, 100);
        System.out.println(num);
        if (num == 99) {
            for (int i = 0; i < list.size(); i++) {
                if (list.get(i).getToyName().equals("PlayStation 5")) {
                    toy = list.get(i);
                    list.remove(i);
                    return toy;
                } else {
                    toy = list.get(0);
                    return toy;
                }
            }
        }
        if (num == 98) {
            for (int i = 0; i < list.size(); i++) {
                if (list.get(i).getToyName().equals("IPhone 15")) {
                    toy = list.get(i);
                    list.remove(i);
                    return toy;
                } else {
                    toy = list.get(0);
                    return toy;
                }
            }
        }
        if (num > 0 && num < 10) {
            for (int i = 0; i < list.size(); i++) {
                if (list.get(i).getToyName().equals("Модель Mercedes G55 AMG")) {
                    toy = list.get(i);
                    list.remove(i);
                    return toy;
                }
            }
        }
        if (num > 9 && num < 20) {
            for (int i = 0; i < list.size(); i++) {
                if (list.get(i).getToyName().equals("Модель Toyota LC 200")) {
                    toy = list.get(i);
                    list.remove(i);
                    return toy;
                }
            }
        }
        if (num > 19 && num < 35) {
            for (int i = 0; i < list.size(); i++) {
                if (list.get(i).getToyName().equals("Модель Lexus IS 250")) {
                    toy = list.get(i);
                    list.remove(i);
                    return toy;
                }
            }
        }
        if (num > 34 && num < 50) {
            for (int i = 0; i < list.size(); i++) {
                if (list.get(i).getToyName().equals("Модель BMW M550i xDrive")) {
                    toy = list.get(i);
                    list.remove(i);
                    return toy;
                }
            }
        }
        return toy;
    }

    public static int introduction() {
        System.out.println("Для розыгрыша игрушки нажмите '1' для выхода - '0'");
        Scanner scanner = new Scanner(System.in);
        int roll = scanner.nextInt();
        return roll;
    }
}
