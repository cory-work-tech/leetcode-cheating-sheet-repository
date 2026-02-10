The Problem:
    Cek palindrom angka

    Ex1:
        Input: x = 121
        Output: true
        Explanation: 121 reads as 121 from left to right and from right to left.
    Ex2:
        Input: x = -121 
        Output: false
        Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.
    Ex3:
        Input: x = 10
        Output: false
        Explanation: Reads 01 from right to left. Therefore it is not a palindrome.

Algoritm Thinking:

    cek dulu if >0 karena harus positif.
    Palindrom itu intinya kita cek digit satu per satu. Kalau number dia traverse via modulo 10, misalnya 121 itu 12 sisa 1 tapi hasilnya jadi 12. 12 modulo 10 itu 1. 1 modulo 10 itu 0 sisa 1.
    kita jadikan sisa 1 nya jadi last digit.

    ceknya itu, reversed = reversed * 10 + lastDigit;  reversed itu mulai dari 0. Intinya kita construct dari kiri. Misalnya 121. Jangan lupa hapus digit pake bagi 10.
    iterasi ke-1:
        x = 121
        last digit = 1
        reversed = 0 * 10 + 1 = 1
        x bagi 10 
    
    iterasi ke-2:
        x = 12
        last digit = 2
        reversed = 1 * 10 + 2 = 12
        x bagi 10

    iterasi ke-3:
        x = 1
        last digit = 1
        reversed 12 * 10 + 1 = 121
        x bagi 10

    setelah selesai, cek apakah original dan reversednya membuat angka yang sama.

Implementing Algorithm:

    public boolean isPalindrome(int x) {
        if (x < 0) return false; 
        int original = x; 
        int reversed = 0; 
        while (x != 0) { 
            int lastDigit = x % 10; 
            // ambil digit terakhir 
            reversed = reversed * 10 + lastDigit; 
            // susun balik 
            x = x / 10; 
            // buang digit terakhir 
            } 
            return original == reversed;
    }
