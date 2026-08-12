#include <iostream>
#include <chrono>

using namespace std;
using namespace std::chrono;

// Iterative Factorial
// Time Complexity: O(n)
// Space Complexity: O(1)
unsigned long long factorialIterative(int n) {
    unsigned long long fact = 1;
    for (int i = 2; i <= n; ++i)
        fact *= i;
    return fact;
}

// Recursive Factorial
// Time Complexity: O(n)
// Space Complexity: O(n)
unsigned long long factorialRecursive(int n) {
    return (n < 2) ? 1 : n * factorialRecursive(n - 1);
}

// Generic function to measure execution time
template <typename Func>
double measureExecution(Func func, int n, unsigned long long &result) {
    auto start = high_resolution_clock::now();
    result = func(n);
    auto stop = high_resolution_clock::now();

    return duration<double, nano>(stop - start).count();
}

int main() {
    int n;

    cout << "Enter a non-negative integer (e.g., 20): ";

    if (!(cin >> n) || n < 0) {
        cerr << "Invalid input! Please enter a non-negative integer." << endl;
        return 1;
    }

    unsigned long long iterativeResult, recursiveResult;

    double iterativeTime = measureExecution(factorialIterative, n, iterativeResult);
    double recursiveTime = measureExecution(factorialRecursive, n, recursiveResult);

    cout << "\n--- Results for " << n << "! ---" << endl;
    cout << "Iterative Result : " << iterativeResult << endl;
    cout << "Iterative Time   : " << iterativeTime << " ns" << endl;
    cout << "-------------------------------" << endl;
    cout << "Recursive Result : " << recursiveResult << endl;
    cout << "Recursive Time   : " << recursiveTime << " ns" << endl;

    return 0;
}
