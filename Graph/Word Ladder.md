# Word Ladder
Given a begin word, an end word and a dictionary, find the least number transformations from begin word to end word, and return the length of the transformation sequence. Return 0 if there is no such transformations.

In each transformation, you can only change one letter, and the word should still in the dictionary after each transformation. 

## Clarification
1. all the words have same length
2. All words contain only lowercase alphabetic characters.
3. There is no duplicates in the word list.
4. The beginWord and endWord are non-empty and are not the same.
5. if the endWord does not exit in dictonary, return 0;

input: a list of words, a beginWord, a endWord
output: an Integer that represent the length of transformation

## General Idea
1. transfer the list of words into a set
2. use bfs
   1. if current word is equal to endWord, return current level.
   2. in each level, change a letter of the word.
   3. if the word after change is existed in the set, put it into the queue.

## Code
```java
public class Solution{
    public int wordLadder(List<String> words, String beginWord, String endWord){
        Set<String> list = new HashSet<>(words);
        if(! list.contains(endWord)) return 0;
        return bfs(list, beginWord, endWord);
    }
    
    // return the shorest length of transformation
    private int bfs(Set<String> list, String beginWord, String endWord){
        Queue<String> queue = new ArrayDeque<>();
        Set<String> visited = new HashSet<>();
        queue.offer(beginWord);
        visited.add(beginWord);
        
        int length = 0;
        while(! queue.isEmpty()){
            int size = queue.size();
            for(int i = 0; i < size; i++){
                String cur = queue.poll();
                if(cur.equals(endWord)) return length;
                // expand cur word
                char[] curChar = cur.toCharArray();
                for(int i = 0; i < curChar.length; i++){
                    char orgin = curChar[i];
                    for(int j = 0; j < 25; j++){
                        char c = 'a' + j;
                        if(c == orgin) continue;
                        curChar[i] = c;
                        String newStr = new String(curChar);
                        if(! visited.contains(newStr) && list.contains(newStr)){
                            queue.offer(newStr);
                        }
                    }
                    curChar[i] = orgin;
                }
            }
            length ++;
        }
        return 0;
    }
}
```

TC = O(n + 26 * L * n) = O(L * n)

SC = O(n + n + n 26 * L * n) = O(L * n)

