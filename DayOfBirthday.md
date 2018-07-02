# Lesson-KPI
hometasks and other 

// ДЕНЬ НАРОДЖЕННЯ.cpp: определяет точку входа для консольного приложения.
//
#include "stdafx.h"
#include <iostream>
#include <string>
#include <locale>
#include <Windows.h>8

using namespace std;


class DayOfBirthday  // клас
{
public:
	int _day; // поле класа
	int _month;
	int _year;

	DayOfBirthday() // конструктор за замовчуванням
	{
		_day = 1;
		_month = 1;
		_year = 1900;
	}

	DayOfBirthday(int day, int month, int year) // конструктор з параметром
	{
		this->_day = DayCheck(day);

		this->_month = MonthCheck(month);

		this->_year = year;

	}


	int DayCheck(int day) // перевірка правильності введення дня місяця
	{
		try
		{
			if ((day < 1) || (day > 31))
			{
				throw "ПОМИЛКА!!!"; // генерація авторської помилки 
			}
			else { return (day); };    // якщо перевірка була вдалою, то функція повертає значення дати (дня)
		}
		catch (const char* i)
		{
			cout << i << endl;
			return 0;
		}

	}


	int MonthCheck(int month) // перевірка правильності введення місяця
	{
		try
		{
			if ((month < 1) || (month > 12))
			{
				throw "ПОМИЛКА!!!"; // генерація авторської помилки 
			}
			else { return (month); };    // якщо перевірка була вдалою, то функція повертає значення місяця
		}
		catch (const char* i)
		{
			cout << i << endl;
			return 0;

		}

	}

	int YearCheck(int year) // перевірка правильності введення року
	{
		try
		{
			if ((year < 1900) || (year > 2018))
			{
				throw "ПОМИЛКА!!!"; // генерація авторської помилки 
			}
			else { return (year); };    // якщо перевірка була вдалою, то функція повертає значення місяця
		}
		catch (const char* i)
		{
			cout << i << endl;
			return 0;

		}

	}


	void Show()
	{
		cout << _day << "\n";
		cout << _month << "\n";
		cout << _year << "\n";

	}

};



void MonthCheck(int month) // перевірка правильності введення дня місяця
{
	if (month < 1)
	{
		cout << "Ви ввели не коректно місяць";
	}
	if (month > 12)
	{
		cout << "Ви ввели не коректно місяць";
	}
}



int main()
{
	setlocale(LC_ALL, "UKR");
	SetConsoleCP(1251);
	SetConsoleOutputCP(1251);

	int a, b, c;
	cout << "Введіть день народження першої людини:" << endl;
	cin >> a;
	cout << "Введіть місяць народження першої людини:" << endl;
	cin >> b;
	cout << "Введіть рік народження першої людини:" << endl;
	cin >> c;

	DayOfBirthday FirstHuman(a, b, c);
	

	system("pause");

	return 0;
}

