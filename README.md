#include <iostream>
#include <iomanip>

double celsiusToFahrenheit(double celsius) {
    return (celsius * 9.0/5.0) + 32.0;
}

double celsiusToKelvin(double celsius) {
    return celsius + 273.15;
}

double fahrenheitToCelsius(double fahrenheit) {
    return (fahrenheit - 32.0) * 5.0/9.0;
}

double fahrenheitToKelvin(double fahrenheit) {
    return (fahrenheit + 459.67) * 5.0/9.0;
}

double kelvinToCelsius(double kelvin) {
    return kelvin - 273.15;
}

double kelvinToFahrenheit(double kelvin) {
    return (kelvin * 9.0/5.0) - 459.67;
}

int main() {
    double temperature;
    char unit;

    std::cout << "Enter the temperature value: ";
    std::cin >> temperature;
    std::cout << "Enter the unit of measurement (C for Celsius, F for Fahrenheit, K for Kelvin): ";
    std::cin >> unit;

    std::cout << std::fixed << std::setprecision(2);

    switch (unit) {
        case 'C':
        case 'c':
            std::cout << "Temperature in Fahrenheit: " << celsiusToFahrenheit(temperature) << " F\n";
            std::cout << "Temperature in Kelvin: " << celsiusToKelvin(temperature) << " K\n";
            break;
        case 'F':
        case 'f':
            std::cout << "Temperature in Celsius: " << fahrenheitToCelsius(temperature) << " C\n";
            std::cout << "Temperature in Kelvin: " << fahrenheitToKelvin(temperature) << " K\n";
            break;
        case 'K':
        case 'k':
            std::cout << "Temperature in Celsius: " << kelvinToCelsius(temperature) << " C\n";
            std::cout << "Temperature in Fahrenheit: " << kelvinToFahrenheit(temperature) << " F\n";
            break;
        default:
            std::cerr << "Invalid unit of measurement entered.\n";
            break;
    }

    return 0;
}
