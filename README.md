#include <iostream>
#include <string>
#include <cmath>
using namespace std;

// Base class
class Shape {
protected:
    string color;

public:
    // Constructor
    Shape(string c) : color(c) {}

    // Virtual Destructor
    virtual ~Shape() {
        cout << "Shape object with color " << color << " terminated." << endl;
    }

    void setColor(string c) {
        color = c;
    }

    string getColor() const {
        return color;
    }
};

// Derived class: Rectangle
class Rectangle : public Shape {
private:
    float length;
    float width;

public:
    // Constructor
    Rectangle(float l, float w, string c) : Shape(c), length(l), width(w) {}

    // Destructor
    ~Rectangle() {
        cout << "Rectangle object terminated." << endl;
    }

    float area() const {
        return length * width;
    }
};

// Derived class: Circle
class Circle : public Shape {
private:
    float radius;

public:
    // Constructor
    Circle(float r, string c) : Shape(c), radius(r) {}

    // Destructor
    ~Circle() {
        cout << "Circle object terminated." << endl;
    }

    float area() const {
        return M_PI * radius * radius;
    }
};

int main() {
    Rectangle rect(10, 5, "Red");
    Circle circ(7, "Blue");

    cout << "Rectangle Color: " << rect.getColor() << endl;
    cout << "Rectangle Area: " << rect.area() << endl;

    cout << "Circle Color: " << circ.getColor() << endl;
    cout << "Circle Area: " << circ.area() << endl;

    return 0;
}
