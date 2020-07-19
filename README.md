# OOPS-concept
This project is done using many oops concept  for Online Movie Ticket Booking.
#include<iostream>
using namespace std;
#include<string.h>
class login
{
	protected:
		string email_id;
		int password;
};
class movie:virtual public login
{
	private:
	int	m_id;
	string m_name;
	string	m_payment;
	string	m_timings;
	public:
	void read();
	void display();
};
	void movie::read()
		{
		cout<<"email-id"<<endl;
		cin>>email_id;
		cout<<"password"<<endl;
		cin>>password;
		
		
		if(password>9999)
		{
		cout<<"\n invalid password\n";
		cout<<"\n enter the correct password:";
		cin>>password;
		cout<<"\n the password is ****"<<endl;
		cout<<"your password is strong"<<endl;
		}
		else 
		{
			cout<<"\n valid password\n";
			cout<<"the password is ****"<<endl;
		}

		cout<<"enter the movie id:"<<endl;
       cin>>m_id;
       cout<<"enter the value for movie payment:"<<endl;
       cin>>m_payment;
       cout<<"enter the value for movie timing:"<<endl;
        cin>>m_timings;
        cout<<"enter the value for movie name:"<<endl;
        cin>>m_name;
        
    }
	void movie::display()
	{
		
	cout<<"the email id"<<email_id<<endl;
	cout<<"password is"<<password<<endl;
	cout<<"for booking the movie id is:"<<m_id<<endl;
       cout<<"the movie payment:"<<m_payment<<endl;
        cout<<"the movie timing is:"<<m_timings<<endl;
        cout<<"the booked movie name is:"<<m_name<<endl;
}

class reservation
{
protected:
	int  theatre_id;
	int debit_card;
	string timings;
	string movie_name;
public:
void read1();
void display1();
};
class ticket: public movie,public reservation
{
private:
int t_no,t_spectator_rates,t_price,t_tax;
string t_type;
public:
void read()
{
	cout<<"enter the reservation theatre id:"<<endl;
	cin>>theatre_id;
	cout<<"enter  the  reservation  debit card value:"<<endl;
	cin>>debit_card;
	cout<<"enter the reservation timing:"<<endl;
	cin>>timings;
	cout<<"enter thhe movie_name"<<endl;
	cin>>movie_name;	
cout<<"enter the ticket number:"<<endl;
cin>>t_no;
cout<<"enter the  value for  ticket spectator  rates:"<<endl;
cin>>t_spectator_rates;
cout<<"enter the price of the ticket:"<<endl;
cin>>t_price;
cout<<"enter the ticket tax:"<<endl;
cin>>t_tax;
cout<<"enter the ticket type:"<<endl;
cin>>t_type;
}

void result()
{
	cout<<"the reservation theatre is:"<<theatre_id<<endl;
    cout<<"the reservation debit card is:"<<debit_card<<endl;
    cout<<"the reservation timing is:"<<timings<<endl;
     cout<<"the reserved movie name is:"<<movie_name<<endl;
        cout<<"the ticket number is:"<<t_no<<endl;
   cout<<"the ticket spectator rates is:"<<t_spectator_rates<<endl;
   cout<<"the ticket type is:"<<t_type<<endl; 

}
friend void cal(ticket);
};
void  cal(ticket t)
{
	int total_price;
	total_price=t.t_price+t.t_tax;
	cout<<"total amount"<<total_price;
}
int main()
{
	movie m;
	m.read();
	m.display();
	ticket a;
	a.read();
	a.result();
	cal(a);
	return 0;
	
}
