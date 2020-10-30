# nomer3package Main;
import java.util.List;

public class Compare {

    private static List ADD(List list, int count){
        for (int i = 0; i < count; i++)
            list.add(i);
        return list;
    }

    public static long Method_add1(List list, int count) {
        long start = System.currentTimeMillis();
        for (int i = 0; i < count; i++)
            list.add(i);
        long end = System.currentTimeMillis();
        return (end-start);
    }
    public static long Method_add2(List list, int count) {
        long start = System.currentTimeMillis();
        for (int i = 0; i < count / 100; i++)
            list.add(0, i);
        long end = System.currentTimeMillis();
        return (end - start);
    }
    public static long Method_get1(List list, int count) {
        list=ADD(list,count);
        long start = System.currentTimeMillis();
        for (int i = 0; i < count/100; i++)
            list.get(count/200);
        long end = System.currentTimeMillis();
        return (end - start);
    }
    public static long Method_get2(List list, int count) {
        list=ADD(list,count);
        long start = System.currentTimeMillis();
        for (int i = 0; i < count/10; i++)
            list.get(1);
        long end = System.currentTimeMillis();
        return (end - start);
    }
    public static long Method_remove1(List list, int count) {
        list=ADD(list,count);
        long start = System.currentTimeMillis();
        for (int i = 0; i < count/1000; i++)
            list.remove(count/200);
        long end = System.currentTimeMillis();
        return (end - start);
    }
    public static long Method_remove2(List list, int count) {
        list=ADD(list,count);
        long start = System.currentTimeMillis();
        for (int i = 0; i < count/1000; i++)
            list.remove(0);
        long end = System.currentTimeMillis();
        return (end - start);
    }
    }

package Main;
import java.util.ArrayList;
import java.util.LinkedList;

public class Main {
    public static void main(String[] args) {

        LinkedList<Integer> linkedlist = new LinkedList<>();
        ArrayList<Integer> arraylist = new ArrayList<>();
        int count = 1000000;

        System.out.printf("%-10s%-15s%-15s%n", "   ", "LinkedList ", "ArrayList");
        System.out.println("-------------------------------------------");
        System.out.printf("%-10s%-30s%n", " ", "  метод add(в конец)");
        System.out.println("-------------------------------------------");
        System.out.printf("%-10s%-15d%-15d%n", "count", count, count);
        System.out.printf("%-10s%-15d%-15d%n", "time", Compare.Method_add1(linkedlist, count), Compare.Method_add1(arraylist, count));
        System.out.println("-------------------------------------------");
        System.out.printf("%-10s%-30s%n", " ", "  метод add(в начало)");
        System.out.println("-------------------------------------------");
        System.out.printf("%-10s%-15d%-15d%n", "count", count, count);
        System.out.printf("%-10s%-15d%-15d%n", "time", Compare.Method_add2(linkedlist, count), Compare.Method_add2(arraylist, count));
        System.out.println("-------------------------------------------");
        System.out.printf("%-10s%-30s%n", " ", "  метод get(из середины)");
        System.out.println("-------------------------------------------");
        System.out.printf("%-10s%-15d%-15d%n", "count", count/100, count/100);
        System.out.printf("%-10s%-15d%-15d%n", "time", Compare.Method_get1(linkedlist, count), Compare.Method_get1(arraylist, count));
        System.out.println("-------------------------------------------");
        System.out.printf("%-10s%-30s%n", " ", "  метод get(из начала)");
        System.out.println("-------------------------------------------");
        System.out.printf("%-10s%-15d%-15d%n", "count", count/10, count/10);
        System.out.printf("%-10s%-15d%-15d%n", "time", Compare.Method_get2(linkedlist, count), Compare.Method_get2(arraylist, count));
        System.out.println("-------------------------------------------");
        System.out.printf("%-10s%-30s%n", " ", " метод remove(из середины)");
        System.out.println("-------------------------------------------");
        System.out.printf("%-10s%-15d%-15d%n", "count", count / 1000, count / 1000);
        System.out.printf("%-10s%-15d%-15d%n", "time", Compare.Method_remove1(linkedlist, count), Compare.Method_remove1(arraylist, count));
        System.out.println("-------------------------------------------");
        System.out.printf("%-10s%-30s%n", " ", " метод remove(первый элемент)");
        System.out.println("-------------------------------------------");
        System.out.printf("%-10s%-15d%-15d%n", "count", count / 1000, count / 1000);
        System.out.printf("%-10s%-15d%-15d%n", "time", Compare.Method_remove2(linkedlist, count), Compare.Method_remove2(arraylist, count));
    }
}
