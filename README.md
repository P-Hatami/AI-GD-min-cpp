# AI-GD-min-cpp
Gradient Descent Algorithm for minimizing f function by AI in C++
#include <iostream>
#include <cmath>

double f(double x) {
    // Define your objective function here (e.g., f(x) = x^2).
    return x * x;
}

double gradient(double x) {
    // Compute the gradient of f(x) analytically (e.g., df/dx = 2x).
    return 2 * x;
}

void gradientDescent(double& x, double learningRate, int maxIterations) {
    for (int i = 0; i < maxIterations; ++i) {
        double grad = gradient(x);
        x -= learningRate * grad;
    }
}

int main() {
    double initialGuess = 2.0;
    double learningRate = 0.1;
    int maxIterations = 100;

    gradientDescent(initialGuess, learningRate, maxIterations);

    std::cout << "Minimum value of f(x) at x = " << initialGuess << ": " << f(initialGuess) << std::endl;

    return 0;
}
