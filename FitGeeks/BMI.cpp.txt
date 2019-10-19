#include "stdafx.h"
#include "iostream"
#include "string"
#include "sstream"

using namespace std;


// BMICalculator function
void BMICalculator()
{
    cout << "Welcome to the BMI Calculator!" << endl; float weightInKilograms;
    float heightInCentimeters; // Should be int but is float so heightInMeters is correctly calculated
    float heightInMeters;
    float BMI;

    cout << endl;

    // User has to input their weight in kilograms (float)
    {
        cout << "Input your weight in kilograms: ";
        cin >> weightInKilograms;

        // Loops as long as cin fails (if input is NOT of type float)
        while (cin.fail())
        {
            cout << "Error: Enter a number!" << endl;
            cin.clear();
            cin.ignore(256, '\n');
            cin >> weightInKilograms;
        }
    }
    // User has to input their height in centimeters (float)
    {
        cout << "Input your height in centimeters: ";
        cin >> heightInCentimeters;

        // Loops as long as cin fails (if input is NOT of type float)
        while (cin.fail())
        {
            cout << "Error: Enter a number!" << endl;
            cin.clear();
            cin.ignore(256, '\n');
            cin >> heightInCentimeters;
        }
    }

    // Converts heightInCentimeters to heightInMeters for calculating the BMI
    heightInMeters = heightInCentimeters / 100;

    // BMI formula
    BMI = weightInKilograms / (heightInMeters * heightInMeters);

    cout << "Your BMI (Body Mass Index) is " << BMI << " kilograms per cubic meter." << endl;
}

// BMRCalculator function
void BMRCalculator()
{
    cout << "Welcome to the BMR Calculator!" << endl << endl;

    int ageInYears;
    char gender;
    float weightInKilograms;
    float heightInCentimeters;
    float BMR;

    // User has to input their age in years (int)
    {
        cout << "Input your age in years: ";
        cin >> ageInYears;

        // Loops as long as cin fails (if input is NOT of type int)
        while (cin.fail())
        {
            cout << "Error: Enter a whole number!" << endl;
            cin.clear();
            cin.ignore(256, '\n');
            cin >> ageInYears;
        }
    }

    // User has to input their gender (male M or female F) (char)

    {
        // If the input (char) isn't either 'M' or 'F' repeat until it is
        do {
            cout << "Input your gender (male 'M' or female 'F'): ";
            cin.ignore();
            cin >> gender;
        } while (gender != 'M' && gender != 'F');
    }



    // User has to input their weight in kilograms (float)
    {
        cout << "Input your weight in kilograms: ";
        cin >> weightInKilograms;

        // Loops as long as cin fails (if input is NOT of type float)
        while (cin.fail())
        {
            cout << "Error: Enter a number!" << endl;
            cin.clear();
            cin.ignore(256, '\n');
            cin >> weightInKilograms;
        }
    }

    // User has to input their height in centimeters (float)
    {
        cout << "Input your height in centimeters: ";
        cin >> heightInCentimeters;

        // Loops as long as cin fails (if input is NOT of type float)
        while (cin.fail())
        {
            cout << "Error: Enter an integer number!" << endl;
            cin.clear();
            cin.ignore(256, '\n');
            cin >> heightInCentimeters;
        }
    }

    cout << endl;


    if (gender = 'M')
    {
        BMR = 10 * weightInKilograms + 6.25 * heightInCentimeters - 5 * ageInYears + 5;
    }

    else if (gender = 'F')
    {
        BMR = 10 * weightInKilograms + 6.25 * heightInCentimeters - 5 * ageInYears - 161;
    }

    cout << "Your BMR (Basal Metabolic Rate) is: " << BMR << endl;
    cout << "This is how much calories your body needs to maintain itsself." << endl;

}

// ToolSelection function
void ToolSelection()
{
    // User input to open a certain function
    string commandString;

    // All available tools in main - update everytime a new tool is added
    {
        cout << "To calculate your BMI (Body Mass Index) type 'BMI'" << endl;
        cout << "To calculate your BMR (Basal Metabolic Rate) type 'BMR'" << endl;
        cout << "To exit the program type 'EXIT'" << endl;
    }

    // Gets the user input (string)
    getline(cin, commandString);

    do {
        // If user input is "BMI" open the BMICalculator
        if (commandString == "BMI")
        {
            BMICalculator();
        }

        // If user input is "BMR" open the BMRCalculator
        else if (commandString == "BMR")
        {
            BMRCalculator();
        }
        // If no valid tool is called let the user choose again
        else
        {
            cout << "Enter a valid input for a tool you want to use!" << endl;
            cin.clear();
            getline(cin, commandString);
        }
    } while (commandString != "BMI" || commandString != "BMR"); // Update everytime a new possible commandString is introduced
}

// Gets called at the start - all other functions have to be written before it so the compiler knows of them!
int main()
{
    cout << "Welcome to my first program - Romans Fitness Tools!" << endl << endl;

    ToolSelection();

    return 0;
}    
