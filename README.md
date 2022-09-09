# ORDER-PROCESS JAVA PROGRAMMING LANGUAGE
Need to use METHOD OVERLOADING but I don't know how to do that.


import java.util.Scanner;

public class Main {



    public static void main(String[] args) {
       int quantity = 0, total = 0, pay=0, sales=0;
       double pay1 = 0, change=0;
       char yn;
       String sz = null;
 
       System.out.println("WELCOME TO TISOY'S FISH FARM");
       System.out.println("");
       System.out.println("     "+"TETRA");
       System.out.println("1. GREEN/PURPLE GLOWFISH = 40.00");
       System.out.println("2. SERPAE = 15.00");
       System.out.println("3. ALBINO TETRA = 7.00");
       System.out.println("4. RED CROSS TETRA = 7.00");
       System.out.println("");
       System.out.println("     "+"BARB");
       System.out.println("5. TIGER BARB = 5.00/BIG 10.00");
       System.out.println("6. ROSY BARB = 5.00");
       System.out.println("7. PLATINUM SUMATRA BREEDER = 20.00");
       System.out.println("8. TINFOIL = 40.00");
       System.out.println("");
       System.out.println("     "+"GURAME");
       System.out.println("9. GOLDEN GURAME = 14.00");
       System.out.println("10. CHOCOLATE GURAME = 45.00");
       System.out.println("");
       do{
       System.out.println("");
       System.out.print("WHAT IS YOUR ORDER? ");
       Scanner in = new Scanner(System.in);
       int order = in.nextInt();
       
       //PARA MATAWAG ANG MGA FUNCTION
       switch(order){
           case 1: pay=one(quantity);
          // System.out.println(one(quantity));
           break;
           case 2: 
               pay=two(quantity);
           break;
           case 3: 
               pay=three(quantity);
           break;
           case 4: 
               pay=four(quantity);
           break;
           case 5: 
               pay=five(quantity,sz,total);
           break;
           case 6: 
               pay=six(quantity);
           break;
           case 7: 
               pay=seven(quantity);
           break;
           case 8: 
               pay=eight(quantity);
           break;
           case 9: 
               pay=nine(quantity);
           break;
           case 10: 
               pay=ten(quantity);
           break;
           default: System.out.println("NOT FOUND IN THE MENU!");
       }

       sales+=pay;
       System.out.print("DO YOU WANT TO ORDER MORE [Y/N]: ");
       Scanner en = new Scanner(System.in);
       yn = en.next().charAt(0);
       }
       while(yn=='Y'||yn=='y');
       
       //FOR COMPUTATION NG MGA PINAMILI
       System.out.println("\nTotal Sales: " +sales);
       if(sales>=5000&&sales<=10000){
           double dis = sales*0.05;
           System.out.println("DISCOUNTED: "+dis);
           pay1 = sales-dis;
           System.out.println("PLEASE PAY: "+pay1);
       }
       if(sales>10000&&sales<=20000){
           double dis = sales*0.10;
           System.out.println("DISCOUNTED: "+dis);
           pay1 = sales-dis;
           System.out.println("PLEASE PAY: "+pay1);
       }
       if(sales>20000){
           double dis = sales*0.15;
           System.out.println("DISCOUNTED: "+dis);
           pay1 = sales-dis;
           System.out.println("PLEASE PAY: "+pay1);
       }
       
       System.out.print("Enter Cash: ");
       Scanner cs = new Scanner(System.in);
       int cash = cs.nextInt();
       while(cash<pay1){
          System.out.println("SORRY YOUR CASH IS NOT ENOUGH");
          System.out.print("Enter Cash: ");
          Scanner sc = new Scanner(System.in);
          cash = sc.nextInt();
       }
       if(cash>=pay1&&cash>=5000){
           change=cash-pay1;
           System.out.println("YOUR CHANGE IS: "+change);
       }
       if(cash<5000){
       while(cash<sales){
          System.out.println("SORRY YOUR CASH IS NOT ENOUGH");
          System.out.println("Enter Cash: ");
          Scanner ch = new Scanner(System.in);
          cash = ch.nextInt();
       }
          change=cash-sales;
          System.out.println("YOUR CHANGE IS: "+change);
       }
       System.out.println("\nTHANK YOU! COME AGAIN");
    }
    
    //TETRA
    public static int one(int qtty){
     System.out.println("YOU ORDERED GREEN/PURPLE GLOWFISH ");
     System.out.println("ENTER QUANTITY: ");
     Scanner qn = new Scanner(System.in);
     qtty = qn.nextInt();
     return (qtty*40); 
    }
    public static int two(int qtty){
     System.out.println("YOU ORDERED SERPAE");
     System.out.println("ENTER QUANTITY: ");
     Scanner qn = new Scanner(System.in);
     qtty = qn.nextInt();
     return (qtty*15);
    }
    public static int three(int qtty){
     System.out.println("YOU ORDERED ALBINO TETRA");
     System.out.println("ENTER QUANTITY: ");
     Scanner qn = new Scanner(System.in);
     qtty = qn.nextInt();
     return (qtty*7);
    }
    public static int four(int qtty){
     System.out.println("YOU ORDERED RED CROSS TETRA");
     System.out.println("ENTER QUANTITY: ");
     Scanner qn = new Scanner(System.in);
     qtty = qn.nextInt();
     return (qtty*7);
    }
    
    //BARB
    public static int five(int qtty, String size, int total){
     System.out.println("YOU ORDERED TIGER BARB");
     System.out.println("ENTER QUANTITY: ");
     Scanner qn = new Scanner(System.in);
     qtty = qn.nextInt();
     System.out.println("SMALL/BIG: ");
     Scanner sb = new Scanner(System.in);
     size = sb.nextLine();
     if("SMALL".equals(size)){
         total=qtty*5;
     }
     if("BIG".equals(size)){
         total=qtty*10;
     }
     return total;
    }
    public static int six(int qtty){
     System.out.println("YOU ORDERED ROSY BARB");
     System.out.println("ENTER QUANTITY: ");
     Scanner qn = new Scanner(System.in);
     qtty = qn.nextInt();
     return (qtty*5);
    }
    public static int seven(int qtty){
     System.out.println("YOU ORDERED PLATINUM SUMATRA BREEDER");
     System.out.println("ENTER QUANTITY: ");
     Scanner qn = new Scanner(System.in);
     qtty = qn.nextInt();
     return (qtty*20);
    }
    public static int eight(int qtty){
     System.out.println("YOU ORDERED TINFOIL");
     System.out.println("ENTER QUANTITY: ");
     Scanner qn = new Scanner(System.in);
     qtty = qn.nextInt();
     return (qtty*40);
    }
    
    //GURAME
    public static int nine(int qtty){
     System.out.println("YOU ORDERED GOLDEN GURAME");
     System.out.println("ENTER QUANTITY: ");
     Scanner qn = new Scanner(System.in);
     qtty = qn.nextInt();
     return (qtty*14);
    }
    public static int ten(int qtty){
     System.out.println("YOU ORDERED CHOCOLATE GURAME");
     System.out.println("ENTER QUANTITY: ");
     Scanner qn = new Scanner(System.in);
     qtty = qn.nextInt();
     return (qtty*45);
    }
   
}
