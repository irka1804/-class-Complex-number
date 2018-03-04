#include <cmath>
#include <iostream>

class Complex {
 private:
    double x, y;
 public:
    Complex(double x = 0.0, double y = 0.0): x(x), y(y) {
    }

    double Re() const {
        return x;
    }

    double Im() const {
        return y;
    }

    double abs() const {
        return std::sqrt(x * x + y * y);
    }
};

double abs(const Complex& a) {
    return a.abs();
}

bool operator == (const Complex& a, const Complex& b) {
    return abs(a.Re() - b.Re()) < 0.000001 && abs(a.Im() - b.Im()) < 0.000001;
}

bool operator != (const Complex& a, const Complex& b) {
    return !(a == b);
}

Complex operator + (const Complex& a) {
    return a;
}

Complex operator + (const Complex& a, const Complex& b) {
    return Complex(
        a.Re() + b.Re(),
        a.Im() + b.Im());
}

Complex operator + (const Complex& a, const double b) {
    return Complex(
        a.Re() + b,
        a.Im());
}

Complex operator + (const double b, const Complex& a) {
    return a + b;
}

Complex operator - (const Complex& a) {
    return Complex(
        -a.Re(),
        -a.Im());
}

Complex operator - (const Complex& a, const Complex& b) {
    return Complex(
        a.Re() - b.Re(),
        a.Im() - b.Im());
}

Complex operator - (const Complex& a, const double b) {
    return a + (-b);
}

Complex operator - (const double b, const Complex& a) {
    return -a + b;
}

Complex operator * (const Complex& a, const Complex& b) {
    return Complex(
        a.Re() * b.Re() - a.Im() * b.Im(),
        a.Re() * b.Im() + a.Im() * b.Re());
}

Complex operator * (const Complex& a, const double b) {
    return Complex(
        a.Re() * b,
        a.Im() * b);
}

Complex operator * (const double b, const Complex& a) {
    return a * b;
}

Complex operator / (const Complex& a, const double b) {
    if (b == 0)
        return Complex();
    return Complex(
        a.Re() / b,
        a.Im() / b);
}

Complex operator / (const Complex& a, const Complex& b) {
    return (a * Complex(b.Re(), -b.Im()))
            / (b.Re() * b.Re() + b.Im() * b.Im());
}

Complex operator / (const double b, const Complex& a) {
    return Complex(b, 0) / a;
}

std::ostream& operator << (std::ostream& out, const Complex& z) {
    out << z.Re() << " + " << z.Im() << "i";
    return out;
}
