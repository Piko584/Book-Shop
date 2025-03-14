# Book-Shop
//Book Shop By Java


package main;

import java.util.Scanner;

public class Book_Store {

    static Scanner myscanner=new Scanner(System.in);
     
    static String[] books={"java","C","Python"}; 
    static final Double StudentDiscount=0.3;
    static final Double TeacherDiscount=0.6;
    static final Double ClubDiscount=0.8;
     
     public static void main(String[] args) {
         println("----Welcome to our Book Shop----");
         print("Which book do you want ? \nAns : ");
         String userChoice=myscanner.nextLine();
         
         if(books[0].toLowerCase().equals(userChoice.toLowerCase())){
             println("You selected "+books[0]+"book");   
               calculatePrice(books[0]);
          } else  if(books[1].toLowerCase().equals(userChoice.toLowerCase())){
             println("You selected "+books[1]+"book"); 
               calculatePrice(books[1]);
          } else  if(books[2].toLowerCase().equals(userChoice.toLowerCase())){
             println("You selected "+books[2]+"book");
               calculatePrice(books[2]);
          } else {
              println("This book isn't available at this moment :( ");             
          }
           
      }
    
    static void calculatePrice(String bookName){
        print("Who are you ? (Student/Teacher/Club ember) \n Ans : ");
        String answer=myscanner.nextLine();
        
        double price= 200;
        
        if(answer.toLowerCase().equals("teacher")){
            price=price-(price*StudentDiscount);
            showprice(price);
        } else  if(answer.toLowerCase().equals("student")){
            price=price-(price*TeacherDiscount);
            showprice(price);
        } else  if(answer.toLowerCase().equals("clubmember")){
            price=price-(price*ClubDiscount);
            showprice(price);
        } else {
            println (" You Entered wrong information");           
        }
    }
    
    static void showprice (double price){
        println("Your payment ammount is :"+price);
        println("-----THANK YOU FOR SHOPPING-----");
        
    }
}
