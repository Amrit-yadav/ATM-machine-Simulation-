import java.util.Scanner;
class Abc 
{
    Scanner sc= new Scanner(System.in);
    private int a,b,c,d,e,f,g,h,i,ac_bal=21000,atm_amount=100000,pin=1234,pin1;

    public void input()
    {

            while(true)
            {
                System.out.println("\n\t\t\t\tWELCOME TO ATM MACHINE\n\n");
                System.out.println("\t\t\t\tEnter your pin ");
                System.out.printf("\t\t\t\t");
                pin1=sc.nextInt();
                if(pin1==pin) {
                    System.out.println("\n\n\t\t\t\tWelcome to Bank Atm\n");
                    System.out.println("\t\t\t\t\tMenu\n");
                    System.out.println("\t\t\t\t1. Balance Enquiary");
                    System.out.println("\t\t\t\t2. Withdraw");
                    System.out.println("\t\t\t\t3. Deposit");
                    System.out.println("\t\t\t\t4. Change PIN");
                    System.out.println("\t\t\t\t5. Exit\n");
                    System.out.println("\t\t\t\tEnter your choice ");
                    System.out.printf("\t\t\t\t");
                    int ch = sc.nextInt();

                    switch (ch) {

                        case 1:
                            balance();
                            break;

                        case 2:
                            withdraw();
                            break;

                        case 3:
                            deposit();
                            break;

                        case 4:
                            change_pin();
                            break;

                        case 5:
                            exit();
                            break;

                        default:
                            System.out.print("\n\t\t\t\tInvalid Choice");
                    }
                }

                else
                {
                    System.out.println("\n\t\t\t\tIncorrect Pin");
                }
            }



    }
    public void balance()
    {
        System.out.println("\n\t\t\t\tYour balance is : "+ac_bal);

    }
    public void change_pin()
    {
        System.out.println("\t\t\t\tEnter new pin");
        System.out.printf("\t\t\t\t");
        pin=sc.nextInt();
        System.out.println("\t\t\t\tYour pin has been changed successfully");
        System.out.println("\t\t\t\tYour new pin is : "+pin);

    }

    public void deposit() {
        int l;
        System.out.println("\n\n\t\t\t\tEnter the amount to be deposited");
        System.out.printf("\t\t\t\t");
        l = sc.nextInt();
        if (l <= 10000) {

            System.out.println("\n\t\t\t\tYour money has been deposited successfully");
            ac_bal += l;
            System.out.println("\n\t\t\t\tYour current balance is :" + (ac_bal));
        }
        else {
            System.out.printf("\t\t\t\t");
            System.out.println("Amount must be less than 10000");
        }
    }

    public void withdraw()
    {

        System.out.println("\n\n\t\t\t\tEnter your amount");
        System.out.println("\t\t\t\tAmount must be in multiple of atleast 50");
        System.out.printf("\t\t\t\t");
        int amount= sc.nextInt();


        if(amount%1000==0||amount%500==0||amount%100==0||amount%50==0)
        {
            if(amount<=ac_bal){
                if(amount<=10000)
                {
                    if(amount<=atm_amount){

                        a=amount/1000;
                        amount=amount%1000;
                        b=amount/500;
                        amount=amount%500;
                        c=amount/100;
                        amount=amount%100;
                        d=amount/50;
                        e=1000*a;
                        f=500*b;
                        g=100*c;
                        h=50*d;
                        i=e+f+g+h;
                        System.out.println("\n\t\t\t\t\tCash Memo");
                        System.out.println("\n\t\t\t\t1000 x "+a+" = "+e);
                        System.out.println("\t\t\t\t500 x "+b+" = "+f);
                        System.out.println("\t\t\t\t100 x "+c+" = "+g);
                        System.out.println("\t\t\t\t50 x "+d+" = "+h);
                        System.out.println("\t\t\t\tTotal Amount = "+i);
                        ac_bal-=i;
                        System.out.println("\n\t\t\t\tYour remaining balance is : "+(ac_bal));
                        System.out.println("\n\t\t\t\tThank you for using Atm");



                    }

                    else{
                        System.out.println("\n\t\t\t\tAtm has insufficient amount");
                    }
                }
                else{
                    System.out.println("\n\t\t\t\t Entered Amount must be less than 10000");
                }
            }
            else
            {
                System.out.println("\n\t\t\t\tInsufficient balance in your account");
            }
        }
        else
        {

            System.out.println("\n\t\t\t\tPlease Enter Valid Amount");
            System.out.println("\n\t\t\t\tYour amount must be in multiple of 50");

        }
    }



    public void exit()
    {

        System.exit(0);

    }
}

class Atm
{


    public static void main(String [] args)
    {

        Scanner sc = new Scanner(System.in);
        Abc A = new Abc();
        A.input();


    }

}
