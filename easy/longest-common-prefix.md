The Problem:
    Write a function to find the longest common prefix string amongst an array of strings.

    If there is no common prefix, return an empty string "".

    Ex1:
        Input: strs = ["flower","flow","flight"]
        Output: "fl"
    Ex2:
        Input: strs = ["dog","racecar","car"]
        Output: ""
        Explanation: There is no common prefix among the input strings.
    Ex3:

Algoritm Thinking:
    Pake vertical scanning. TBD

Implementing Algorithm:

    public String longestCommonPrefix(String[] strs) {
        if (strs == null || strs.length == 0) {
            return "";
        }

        // 2. Gunakan string pertama sebagai acuan (pivot)
        for (int i = 0; i < strs[0].length(); i++) {
            char c = strs[0].charAt(i);

            // 3. Bandingkan karakter ini dengan kata-kata lainnya
            for (int j = 1; j < strs.length; j++) {
                // Periksa apakah indeks 'i' sudah melampaui panjang kata lain
                // ATAU karakter di posisi tersebut sudah berbeda
                if (i == strs[j].length() || strs[j].charAt(i) != c) {
                    // Kembalikan substring dari awal hingga indeks sebelum 'i'
                    return strs[0].substring(0, i);
                }
            }
        }

        // 4. Jika semua karakter di string pertama lolos pengecekan
        return strs[0];
    }
