#include<stdio.h>
#include<string.h>

#define MAX_SEAT 50
#define PER_SEAT_COST 150
#define BAGS_ALLOWED 6
int seat[MAX_SEAT]= {0};
struct reserve
{
    char name[512];
    int seatnum;
    int totalcost;
    char busType[512];
};

struct reserve reservation ;
 
 // Bus type

void busType() {
    printf("=================BUS TYPE======================");
    printf("\n\nDaewoo\n");
    printf("Faisal Movers\n");
    printf("Anderson Travels\n");
    printf("Journey Lines\n");
    printf("Horizon Travels\n");
    printf("GrayHound\n");
    printf("---------------------------------------------");
}

// Display menu
void displayMenu() {
    printf("\n\n==========================WELCOME============================\n\n");
    printf("\n1. Display Available Seats\n");
    printf("2. Reserve a Seat\n");
    printf("3. Cancel Booking\n");
    printf("4. Refund a Seat\n");
    printf("5. Exit\n");
    printf("\n------------------------------------------------------------------------------------------");
}

void availableSeats(int seat[], int size) {

    for(int i=0; i<size; i++) {
        if(seat[i]==0) {
            printf("Seat %d: Available \n\n", i+1);
        }
    }

}

// for reserve the seat
void reserveSeat()
{

    int  bags;
    float totalCost;
    char ch[20];
    char destination[256];

    busType();
    printf("Enter the bus type:");
    scanf("%s", & reservation.busType);

    printf("Enter seat number you want to reserve:");
    scanf("%d",& reservation.seatnum);

    if(reservation.seatnum >= 1  &&  reservation.seatnum <= 50 && seat[reservation.seatnum-1]==0) {
    seat[reservation.seatnum-1]=1;
        printf("Do you have Luggage? yes or no:\n");
        scanf("%s", ch);

        if(strcmp(ch,"yes")==0)
        {
            printf("Enter number of bags:");
            scanf("%d",&bags);

            totalCost= PER_SEAT_COST+(20*bags);

            if(bags > BAGS_ALLOWED)
            {
                printf("------Bag Limit is Exceeded------\n");
                return;
            }
            else
            {
                printf("Enter your name:");
                scanf("%s",& reservation.name);

                printf("Enter the location:");
                scanf("%s", destination);


                printf("\n\n----------- Reservation Info -----------\n\n");

                printf("Seat Reserved!\n");
                printf("Name is: %s\n",reservation.name);
                printf("Seat Number is: %d\n", reservation.seatnum);
                printf("Your Destination is:%s\n", destination);
                printf("Total Cost is: %.2f\n", totalCost);
            }
        }
        else
        {
            printf("Enter your name:");
            scanf("%s",& reservation.name);

            printf("Enter the location:");
            scanf("%s", destination);


            printf("\n\n----------- Reservation Info -----------\n\n");
            printf("Seat Reserved!\n");
            printf("Name is: %s\n",reservation.name);
            printf("Seat Number is: %d\n", reservation.seatnum);
            printf("Your Destination is:%s\n", destination);
            printf("Total Cost is: %d\n", PER_SEAT_COST);
        }
    }
    else {
        printf("Invalid Seat Entered.\nSeat is already Reserved!\n\n");
    }
}
// cancel the seat
void cancelSeat() {
    int seatNum;
    printf("Enter the seat number you want to cancel:");
    scanf("%d",&seatNum);
    if(seatNum>1 && seatNum == reservation.seatnum) {
        printf("Your seat has been cancelled successfully.");
    }    else {
        printf("Invalid Seat number.");
    }

}
// refund the seat
void refundSeat() {
    int seatNum;
    printf("Enter the seat no you want to refund:");
    scanf("%d",&seatNum);
    if(seatNum == reservation.seatnum && seat[reservation.seatnum-1] == 1) {
    seat[reservation.seatnum - 1] = 0;
    float re= (PER_SEAT_COST*20)/100;
    float total= (PER_SEAT_COST-re);
        printf("Refunding %.2f/- for seat %d has been done by deducting 20%", total, seatNum);
    }
    else {
        printf("Invalid Seat number");
    }
}

int main()
{
    int choice;


    do {
        displayMenu();
        printf("\nEnter your choice:");
        scanf("%d", &choice);
        switch(choice) {
        case 1:
            availableSeats(seat, MAX_SEAT);
            break;
        case 2:
            reserveSeat();
            break;
        case 3:
            cancelSeat();
            break;
        case 4:
            refundSeat();
            break;
        case 5:
            printf("--------------------------------------");
            printf("\nTHANK YOU!\nHAVE A GREAT DAY!\n");
            break;
        default:
            printf("Invalid Choice");
        }
    } while(choice!=5);
    return 0;
}
