# -Юст Максим Маринович УИБО-09-24
Вариант 6:

1. С++:

#include <iostream>
#include <string>
using namespace std;

bool isVowel(char c) {
    c = tolower(c);
    return (c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u' || 
            c == 'y' || c == 'а' || c == 'е' || c == 'и' || c == 'о' || 
            c == 'у' || c == 'ы' || c == 'э' || c == 'ю' || c == 'я');
}

int countVowels(const string& str, int index) {
    if (index == str.length()) {
        return 0;
    }    int current = isVowel(str[index]) ? 1 : 0;
    return current + countVowels(str, index + 1);
}

int main() {
    string input;
    cout << "Введите строку: ";
    getline(cin, input);
    
    int result = countVowels(input, 0);
    cout << "Количество гласных: " << result << endl;
    
    return 0;
}

python:

def is_vowel(c):
    c = c.lower()
    return c in 'aeiouyаеиоуыэюя'

def count_vowels(s, index=0):
    if index == len(s):
        return 0
    current = 1 if is_vowel(s[index]) else 0
    return current + count_vowels(s, index + 1)

input_str = input("Введите строку: ")
result = count_vowels(input_str)
print(f"Количество гласных: {result}")

java:

import java.util.Scanner;

public class VowelCounter {
    
    public static boolean isVowel(char c) {
        c = Character.toLowerCase(c);
        return "aeiouyаеиоуыэюя".indexOf(c) != -1;
    }
    
    public static int countVowels(String str, int index) {
        if (index == str.length()) {
            return 0;
        }
        int current = isVowel(str.charAt(index)) ? 1 : 0;
        return current + countVowels(str, index + 1);
    }
    
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Введите строку: ");
        String input = scanner.nextLine();
        
        int result = countVowels(input, 0);
        System.out.println("Количество гласных: " + result);
        
        scanner.close();
    }
}

2. Алгоритм:

Базовый случай: Если index достиг длины строки, возвращаем 0.

Рекурсивный случай:

Проверяем символ в текущей позиции index с помощью вспомогательной функции isVowel.

Если символ гласный, current = 1, иначе current = 0.

Возвращаем current + countVowels(str, index + 1)

Синтаксис:

isVowel(char c): Вспомогательная функция, проверяющая, входит ли символ в строку, содержащую все гласные (английские и русские). Символ предварительно приводится к нижнему регистру.

countVowels(str, index): Основная рекурсивная функция.

str — входная строка.

index — текущий индекс для обработки.

3. Временная сложность:
O(n), n — длина входной строки.

4. Объяснение временной сложности
Функция countVowels выполняет ровно один рекурсивный вызов для каждого символа строки. На каждом шаге выполняется проверка символа (isVowel) — операция O(1). Таким образом, общее количество операций пропорционально длине строки n.

5. Пример ввода/вывода для трех скриптов
Ввод: Введите строку: Hello, Мир!
Вывод (для всех трех программ): Количество гласных: 3

6. Ответ на вопрос №5:

Стратегия «разделяй и властвуй» решает задачу в три этапа:

Разделить - задача разбивается на одинаковые подзадачи меньшего размера

Властвовать - подзадачи решаются рекурсивно

Объединить - решения подзадач комбинируются
