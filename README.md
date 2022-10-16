# ATM
/******************************************************************************

                            Online C Compiler.
                Code, Compile, Run and Debug C program online.
Write your code in this editor and press "Run" button to compile and execute it.

*******************************************************************************/

#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main()
{
    int pin=1234,option,enteredPin,count=0,amount=1;
    float balance=5000;
    int continueTranaction=1;
    time_t now;
    time(&now);
    printf("\n");
    printf("\t\t\t\t\t\t\t%s",ctime(&now));
    printf("\n\t\t\t==============================*Welcome to Adv ATM Mechine*==============================");
    
    while(pin!=enteredPin){
        printf("\n\t\t\tPlease Enter Your Pin: ");
        scanf("%d",&enteredPin);
        if(enteredPin!=pin){
            printf("\n\t\tInvalid Pin!!!");
        }else{
            printf("\n\t\tYour Entered Pin is Correct");
        }
        count++;
        if(count==3&&pin!=enteredPin){
        exit(0);
        }
    }
        while(continueTranaction!=0){
        printf("\n\t\t\t==============================*Available transaction*=================================");
        printf("\n\t\t1.Withdrawl");
        printf("\n\t\t2.Deposit");
        printf("\n\t\t3.Check Balance");
        printf("\n\n\t\tPlease Select the option : ");
        scanf("%d",&option);
        switch(option){
            case 1:
            while(amount%500!=0){
                printf("\n\t\tEnter the amount : ");
                scanf("%d",&amount);
                if(amount%500!=0){
                    printf("\n\t\tThe amount should be multiple of 500");
                }}
                if(balance<amount){
                    printf("\n\t\tSorrt Insufficient balance");
                    amount=1;
                    break;
                }
                else{
                    balance-=amount;
                    printf("\n\t\tYou have withdrawn Rs. %d.Your new balance is %.2f",amount,balance);
                    amount=1;
                    break;
                }
            case 2:
            printf("\n\t\tPlease Enter Amount : ");
            scanf("%d",&amount);
            balance+=amount;
            printf("\n\t\tYou have Deposited Rs.%d and your balance is %.2f",amount,balance);
            printf("\n\t\t===============================Thank you=================================");
            amount=1;
            break;
            case 3:
            printf("\n\t\t Your balance is %.2f",balance);
            break;
            default:
            printf("\n\t\tInvalid Option");
        }
        printf("\n\t\t Dou you want to perform another transaction? 1[yes],0[no] : ");
        scanf("%d",&continueTranaction);
        }
    return 0;
}
