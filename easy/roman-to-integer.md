The Problem:
    Roman numerals are represented by seven different symbols: I, V, X, L, C, D and M.
    
    Symbol       Value
    I             1
    V             5
    X             10
    L             50
    C             100
    D             500
    M             1000

    Ex1:
        Input: s = "III"
        Output: 3
        Explanation: III = 3.
    Ex2:
        Input: s = "LVIII"
        Output: 58
        Explanation: L = 50, V= 5, III = 3.

    Ex3:
        Input: s = "MCMXCIV"
        Output: 1994
        Explanation: M = 1000, CM = 900, XC = 90 and IV = 4.

Algoritm Thinking:

    Definisikan aturan Roman seperti yang ada di atas (Bisa pakai switch case atau hash map). For loop digit setelahnya atau sebelumnya bisa juga. Cek apakah tingkatannya diatas atau bukan. Jika dibawah dikurangi, Jika diatas ditambah.

Implementing Algorithm:
    private int value(char c) {
        return switch (c) {
            case 'I' -> 1;
            case 'V' -> 5;
            case 'X' -> 10;
            case 'L' -> 50;
            case 'C' -> 100;
            case 'D' -> 500;
            case 'M' -> 1000;
            default -> 0;
        };
    }

    public int romanToInt(String s) {
        int total = 0;
        for (int i = 0; i < s.length(); i++) {
            int curr = value(s.charAt(i));
            if (i + 1 < s.length()) {
                int next = value(s.charAt(i + 1));
                if (curr < next) {
                    total -= curr; 
                } else {
                    total += curr; 
                }
            } else {
                total += curr; 
            }
        }
        return total;
    }