The Problem:
    You are given the heads of two sorted linked lists list1 and list2.

    Merge the two lists into one sorted list. The list should be made by splicing together the nodes of the first two lists.

    Return the head of the merged linked list.

    Ex1:
        Input: list1 = [1,2,4], list2 = [1,3,4]
        Output: [1,1,2,3,4,4]
    Ex2:
        Input: list1 = [], list2 = []
        Output: []
    Ex3:
        Input: list1 = [], list2 = [0]
        Output: [0]

Algoritm Thinking:
    Solusi linkedlist biasanaya ada listnode. tapi intinya ini standar while looping dan check list1 dan list2 sampe keduanya null.
    check nilai list1 lebih kecil dari list2 jika iya maka tail.next jadi value list1 list1 dinext, maka berlaku juga jika list2 lebih kecil maka tail.next jadi value list2 dan list2 di next

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