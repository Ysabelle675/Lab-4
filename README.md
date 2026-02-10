# Lab-4
Transcript link: https://share.google/aimode/rUwtEcp2pBcc6I5Yh
Video link: https://www.canva.com/design/DAHAPqTJgSw/pLVbv1VpoSizkusIY9RCQA/edit?utm_content=DAHAPqTJgSw&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton 
Main.cpp link: https://replit.com/@ysanchez76/Lab-4#main.cpp
Hopefully each link works! :)
Code: 
#include <iostream>
#include <iomanip>

using namespace std;

int calculateSum(const int arr[], int size);
double getAverage(int sum, int size);
void addBonus(int arr[], int size, int bonus = 5);
int findHighest(const int* arr, int size);
int countPasses(const int arr[], int size);

void printScores(const int arr[], int size) {
    for (int i = 0; i < size; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;
}

int main() {
    const int SIZE = 5;
    int scores[SIZE] = {65, 82, 90, 45, 78};

    cout << "Original Scores: ";
    printScores(scores, SIZE);

    int totalSum = calculateSum(scores, SIZE);
    double averageScore = getAverage(totalSum, SIZE);
    cout << "Sum: " << totalSum << " Average: " << fixed << setprecision(2) << averageScore << endl;

    addBonus(scores, SIZE);
    cout << "Scores after bonus: ";
    printScores(scores, SIZE);

    cout << "Highest Score: " << findHighest(scores, SIZE) << endl;
    cout << "Number of passing scores: " << countPasses(scores, SIZE) << endl;

    return 0;
}

int calculateSum(const int arr[], int size) {
    int sum = 0;
    for (int i = 0; i < size; i++) {
        sum += arr[i];
    }
    return sum;
}

double getAverage(int sum, int size) {
    return (double)sum / size;
}

void addBonus(int arr[], int size, int bonus) {
    for (int i = 0; i < size; i++) {
        arr[i] += bonus;
    }
}

int findHighest(const int* arr, int size) {
    int maxVal = *arr;
    for (int i = 1; i < size; i++) {
        if (arr[i] > maxVal) {
            maxVal = arr[i];
        }
    }
    return maxVal;
}

int countPasses(const int arr[], int size) {
    int count = 0;
    for (int i = 0; i < size; i++) {
        if (arr[i] >= 70) {
            count++;
        }
    }
    return count;
}
