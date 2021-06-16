# BUS-RESEVATION-SYSTEM
source code
// BUS RESERVATION SYSTEM
#include<iostream>
#include <string>
using namespace std;
int r=0,p=0,k=20;
float TotalSale=0;
class bus{
    char PassengerName[99];
    char departure[9];
    char from[9];
    char to[9];
    char arrivaltime[9];
    int  totalseats, totalprice;
    int BusNo, Departuretime, s;
public:
    void bus_id();
    void show();
    void book();
    void End();
}b[8];
void bus::bus_id(void)
{
    cout<<"\nEnter Bus No:";
    cin>>BusNo;

    cout<<"\nFrom: ";
    cin>>from;

    cout<<"\nTo: ";
    cin>>to;

    cout<<"\nArrival time:";
    cin>>arrivaltime;

    cout<<"\nDeparture: ";
    cin>>Departuretime;

    cout<<"\nTotal seats: ";
    cin>>totalseats;

    p++;
    cout<<"\n";
    cout<<"Bus Information Added!!\n";
    system("PAUSE");
    system("CLS");
}
void bus::show(void)
{
    cout<<"\nTotal bus available:"<<endl;
    for(int i=0;i<p;i++)
    {
        cout<<"Bus No: ";
        cout<<b[i].BusNo<<endl;

        cout<<"From: ";
        cout<<b[i].from<<endl;

        cout<<"To: ";
        cout<<b[i].to<<endl;
        cout<<"Arrival: ";
        cout<<b[i].arrivaltime<<" O'clock"<<endl;

        cout<<"Departure: ";
        cout<<b[i].Departuretime<<" O'clock"<<endl;

        cout<<"Seats: ";
        cout<<b[i].totalseats<<endl<<endl<<endl;
    }
    system("PAUSE");
    system("CLS");
}
void bus::book(void)
{
    int number;
    float totalprice;
    cout<<"\nEnter Bus No: ";
    cin>>number;
    int n;
    for(n=0;n<p;n++)
    {
        if(b[n].BusNo==number)
        {
            if(b[n].totalseats<=0)
            {
                cout<<"\tSORRY!"<<endl<<"\tNo  Seats Available\t";
            }
            else
            {
                cout<<endl<<"Total seat available: "<<b[n].totalseats;
                cout<<endl<<"Enter Passenger's Name: ";
                cin>>PassengerName;
                cout<<endl<<"Number of seats: ";
                cin>>s;
                while((b[n].totalseats=b[n].totalseats-s)<0)
                {
                    cout<<endl<<"Limit Exceed...Please re-enter ";
                    b[n].totalseats=b[n].totalseats+s;
                    cin>>s;
                }
                cout<<endl<<"Your purchase is completed"<<endl;

                cout<<"Bus No: ";
                cout<<b[n].BusNo<<endl;

                                cout<<"From: ";
                cout<<b[n].from<<" to "<<b[n].to<<endl;

                cout<<"Arrival: ";
                cout<<b[n].arrivaltime<<" O'clock"<<endl;

                cout<<"Departure: ";
                cout<<b[n].Departuretime<<" O'clock"<<endl;

                cout<<"Total seat: ";
                cout<<s<<endl;
                totalprice=500*s;
                totalprice=totalprice+(totalprice*.12);
                TotalSale=TotalSale+totalprice;

                cout<<"Total price(with 12%vat): ";

                cout<<totalprice<<endl;

                cout<<"Thank You!!!"<<endl<<endl;
            }
        }
    }
    system("PAUSE");
    system("CLS");
}
int main()
{
    int w,g=1;

    while (g) {
            cout << "\t\t\t\t*******************************" << endl;
            cout << "\t\t\t\tBus Ticket Reservation System\n";
            cout << "\t\t\t\t*******************************" << endl;
            cout
                    << "\t\t\t\t 1 :: bus_id\n\t\t\t\t 2 :: List Available Bus\n\t\t\t\t 3 => Book Tickets\n\t\t\t\t 4 => End";
            cout << "\n\n\t\t\t Enter your choice: ";
            cin >> w;
        string name ;int pass;
        cout<<"enter username : ";
        cin>>name;
        cout<<"Enter password: ";
        cin>>pass;
        if (name=="admin"&& pass==3333) {

            switch (w) {
                case 1:
                    b[p].bus_id();
                    break;
                case 2:
                    b[0].show();
                    break;
                case 3:
                    b[p].book();
                    break;
                case 4: {
                    g = 0;
                    cout << endl << "Total Sales:" << TotalSale << endl;
                    break;
                }
            }
        }
        else {
            cout<<"WRONG credentials ! Enter again  "<<endl;
        }
        }

    return 0;
}

