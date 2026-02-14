The Problem:
    Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

    An input string is valid if:

    Open brackets must be closed by the same type of brackets.
    Open brackets must be closed in the correct order.
    Every close bracket has a corresponding open bracket of the same type.

    Ex1:
        Input: s = "()"
        Output: true
    Ex2:
        Input: s = "()[]{}"
        Output: true
    Ex3:
        Input: s = "(]"
        Output: false
    Ex4:
        Input: s = "([])"
        Output: true
    Ex5:
        Input: s = "([)]"
        Output: false

Algoritm Thinking:
    Buat stack. forloop sekali pake panjang s length. cek jika buka masukin stack. kalau tutup, cek apakah stack kosong = fail, cek isi stack apa sama denga kurung bukaan.

Implementing Algorithm:
    public boolean isValid(String s) {
            // gunakan array char sebagai stack
            char[] stack = new char[s.length()];
            int top = -1;
            // pointer ke posisi atas stack
            for (int i = 0; i < s.length(); i++)
            {
                char c = s.charAt(i);
                // kalau tanda buka, push ke stack
                if (c == '(' || c == '[' || c == '{') {
                    stack[++top] = c; }
                else {
                    // kalau tanda tutup, cek apakah stack kosong
                    if (top == -1) return false;
                    char open = stack[top--];
                    // pop dari stack
                    // cek apakah pasangan sesuai
                    if ((c == ')' && open != '(') || (c == ']' && open != '[') || (c == '}' && open != '{')) {
                        return false;
                    }
                }
            } // valid hanya kalau stack kosong di akhir
            return top == -1;
        }