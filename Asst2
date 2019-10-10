#include <string>
#include <iostream>
#include <iomanip>
#include <fstream>
using namespace std;

/*Nikola Zorica
This program allows the user to enter guests at a hotel. the program takes the guests name, room type, and number of days.
from this it figures out the cost of the room. it keeps track of the amount of guests and the total amount spent by them on rooms.
at the end it figures out the average room fee.*/

int main(){
	//House keeping
	int numbDays, noGuests = 0;
	double roomCost, roomFee, averageRoomFee, toltalRoomFee = 0;
	char roomType;
	string name, roomName;
	ofstream fout("charge.dat");
	while (!fout.is_open())
	{
		cout << "Your file did not open.";
		system("pause");
		exit(666);
	}
	fout << fixed << setprecision(2);
	fout << right << setw(45) << "CPA Resort Hotel Room Charge" << endl;
	fout << left << setw(20) << "Guest Name" << setw(15) << "Room Type" << right << setw(10) << "# Days" << setw(15) << "Room Charge" << endl << endl;
	//input
	cout << "Enter Guest Name. (Ctrl+Z to end). ";
	getline(cin, name);
	while (!cin.eof())
	{
		//WhileInput
		cout << "Enter room type. ";
		cin >> roomType;
		roomType = toupper(roomType);
		while (roomType != 'L' &&roomType != 'G' &&roomType != 'P')
		{
			cin.clear();
			cin.ignore(80, '\n');
			cout << "Invalid input. Please enter L, G or P. ";
			cin >> roomType;
			roomType = toupper(roomType);
		}
		cout << "Enter Number of days of the stay. ";
		cin >> numbDays;
		while (numbDays < 1 || numbDays > 15 || cin.fail())
		{
			cin.clear();
			cin.ignore(80, '\n');
			cout << "Invalid input. Guests can stay between 1 and 15 days. ";
			cin >> numbDays;
		}
		if (roomType == 'L')
		{
			roomName = "Lake View";
			roomFee = 180.0;
		}
		else if (roomType == 'P')
		{
			roomName = "Pool View";
			roomFee = 145.0;
		}
		else
		{
			roomName = "Garden View";
			roomFee = 125.0;
		}
		//WhileProcess
		noGuests++;
		roomCost = roomFee*numbDays;
		toltalRoomFee += roomCost;
		//WhileOutput
		fout << left << setw(20) << name << setw(15) << roomName << right << setw(10) << numbDays << setw(15) << roomCost << endl;
		//WhileRestart
		cin.ignore(80, '\n');
		cout << "Enter Guest Name. (Ctrl+Z to end). ";
		getline(cin, name);
	}
	//Processing
	if (noGuests > 0)
	{
		averageRoomFee = toltalRoomFee / noGuests;
		fout << endl << left << setw(50) << "Average Room Charge" << right << setw(10) << averageRoomFee;
	}

	system("type charge.dat");
	system("pause");
	/*
	Enter Guest Name. (Ctrl+Z to end). Nikola Zorica
	Enter room type. g
	Enter Number of days of the stay. 12
	Enter Guest Name. (Ctrl+Z to end). Brayden Roy
	Enter room type. d
	Invalid input. Please enter L, G or P. l
	Enter Number of days of the stay. 5
	Enter Guest Name. (Ctrl+Z to end). Michael Poulin
	Enter room type. p
	Enter Number of days of the stay. 20
	Invalid input. Guests can stay between 1 and 15 days. 3
	Enter Guest Name. (Ctrl+Z to end). ^Z
				      CPA Resort Hotel Room Charge
	Guest Name          Room Type          # Days    Room Charge

	Nikola Zorica       Garden View            12        1500.00
	Brayden Roy         Lake View               5         900.00
	Michael Poulin      Pool View               3         435.00

	Press any key to continue . . .
	*/

}
