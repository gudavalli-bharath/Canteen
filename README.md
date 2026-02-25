import java.util.Scanner;

public class CollegeCanteenMenu {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        int mainChoice, itemChoice, quantity;
        double total = 0;
        StringBuilder billDetails = new StringBuilder();

        do {
            System.out.println("\n=================================");
            System.out.println("        FRIENDS CANTEEN");
            System.out.println("=================================");
            System.out.println("1. Tiffin Items");
            System.out.println("2. Lunch Items");
            System.out.println("3. Tea & Coffee");
            System.out.println("4. Cool Drinks");
            System.out.println("5. Snacks");
            System.out.println("6. Exit");
            System.out.print("Enter your choice: ");

            mainChoice = sc.nextInt();

            String itemName = "";
            double price = 0;

            switch (mainChoice) {

                case 1:
                    System.out.println("\n--- TIFFIN MENU ---");
                    System.out.println("1. Idly - ₹30");
                    System.out.println("2. Punugulu - ₹40");
                    System.out.println("3. Dosa - ₹50");
                    System.out.println("4. Onion Dosa - ₹60");
                    System.out.print("Select item: ");
                    itemChoice = sc.nextInt();

                    switch (itemChoice) {
                        case 1: itemName = "Idly"; price = 30; break;
                        case 2: itemName = "Punugulu"; price = 40; break;
                        case 3: itemName = "Dosa"; price = 50; break;
                        case 4: itemName = "Onion Dosa"; price = 60; break;
                        default: System.out.println("Invalid item!"); continue;
                    }
                    break;

                case 2:
                    System.out.println("\n--- LUNCH MENU ---");
                    System.out.println("1. Rice Plate - ₹70");
                    System.out.println("2. Veg Curry - ₹50");
                    System.out.println("3. Non-Veg Curry - ₹120");
                    System.out.println("4. Full Meals - ₹150");
                    System.out.println("5. Chicken Biryani - ₹200");
                    System.out.println("6. Mutton Biryani - ₹300");
                    System.out.print("Select item: ");
                    itemChoice = sc.nextInt();

                    switch (itemChoice) {
                        case 1: itemName = "Rice Plate"; price = 70; break;
                        case 2: itemName = "Veg Curry"; price = 50; break;
                        case 3: itemName = "Non-Veg Curry"; price = 120; break;
                        case 4: itemName = "Full Meals"; price = 150; break;
                        case 5: itemName = "Chicken Biryani"; price = 200; break;
                        case 6: itemName = "Mutton Biryani"; price = 300; break;
                        default: System.out.println("Invalid item!"); continue;
                    }
                    break;

                case 3:
                    System.out.println("\n--- TEA & COFFEE ---");
                    System.out.println("1. Tea - ₹10");
                    System.out.println("2. Coffee - ₹15");
                    System.out.println("3. Boost - ₹20");
                    System.out.print("Select item: ");
                    itemChoice = sc.nextInt();

                    switch (itemChoice) {
                        case 1: itemName = "Tea"; price = 10; break;
                        case 2: itemName = "Coffee"; price = 15; break;
                        case 3: itemName = "Boost"; price = 20; break;
                        default: System.out.println("Invalid item!"); continue;
                    }
                    break;

                case 4:
                    System.out.println("\n--- COOL DRINKS ---");
                    System.out.println("1. Water Bottle 500ml - ₹25");
                    System.out.println("2. Thums Up 200ml- ₹20");
                    System.out.println("3. Sprite 200ml- ₹20");
                    System.out.println("4. Maaza 200ml- ₹20");
                    System.out.println("5. Thums Up 1Lr- ₹100");
                    System.out.println("6. Sprite 1Lr- ₹100");
                    System.out.println("7. Maaza 1Lr- ₹100");

                    System.out.print("Select item: ");
                    itemChoice = sc.nextInt();

                    switch (itemChoice) {
                        case 1: itemName = " Water Bottle 500ml"; price = 25; break;
                        case 2: itemName = "Thums Up 200ml"; price = 20; break;
                        case 3: itemName = "Sprite 200ml"; price = 20; break;
                        case 4: itemName = "Maaza 200ml"; price = 20; break;
                        case 5: itemName = "Thums Up 1Lr"; price = 100; break;
                        case 6: itemName = "Sprite 1Lr"; price = 100; break;
                        case 7: itemName = "Maaza 1Lr"; price = 100; break;

                        default: System.out.println("Invalid item!"); continue;
                    }
                    break;

                case 5:
                    System.out.println("\n--- SNACKS ---");
                    System.out.println("1. Samosa - ₹5");
                    System.out.println("2. Chips - ₹10");
                    System.out.println("3. Biscuit - ₹10");
                    System.out.println("4. Veg Puff - ₹25");
                    System.out.println("4. egg Puff - ₹30");
                    System.out.print("Select item: ");
                    itemChoice = sc.nextInt();

                    switch (itemChoice) {
                        case 1: itemName = "Samosa"; price = 5; break;
                        case 2: itemName = "Chips"; price = 10; break;
                        case 3: itemName = "Biscuit"; price = 10; break;
                        case 4: itemName = "Veg Puff"; price = 25; break;
                        case 4: itemName = "egg Puff"; price = 30; break;
                        default: System.out.println("Invalid item!"); continue;
                    }
                    break;

                case 6:
                    System.out.println("Thank you for visiting FRIENDS CANTEEN 😊");
                    break;

                default:
                    System.out.println("Invalid choice!");
                    continue;
            }

            if (mainChoice >= 1 && mainChoice <= 5) {
                System.out.print("Enter quantity: ");
                quantity = sc.nextInt();

                double subTotal = price * quantity;
                total += subTotal;

                billDetails.append(itemName)
                        .append(" x ")
                        .append(quantity)
                        .append(" = ₹")
                        .append(subTotal)
                        .append("\n");
            }

        } while (mainChoice != 6);

        System.out.println("\n=================================");
        System.out.println("         FRIENDS CANTEEN");
        System.out.println("=================================");
        System.out.println("======= BILL RECEIPT =======");
        System.out.println(billDetails);
        System.out.println("Total Amount: ₹" + total);
        System.out.println("============================");

        sc.close();
    }
}
