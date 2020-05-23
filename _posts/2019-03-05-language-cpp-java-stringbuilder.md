---
layout: post
title:  "[Languages] StringBuilder(cpp/java)"
date:   2019-03-05 20:00:00
categories: ProgrammingLanguages
tags: ProgrammingLanguages C++ Java
author: Hailey Gu
---

* content
{:toc}

## StringBuilder example

[link](https://leetcode.com/problems/most-common-word/){:target="_blank"}

### C++
```c++
class Solution {
public:
    string mostCommonWord(string paragraph, vector<string>& banned) {

        unordered_set<string> ban(banned.begin(), banned.end());
        unordered_map<string, int> count;

        for(int i = 0; i < paragraph.length(); i++) {
            if(isalpha(paragraph[i]))
                paragraph[i] = tolower(paragraph[i]);
            else
                paragraph[i] = ' ';
        }

        istringstream iss(paragraph);
        string w;
        pair<string, int> res("",0);
        while(iss >> w) {
            if(ban.find(w) == ban.end() && ++count[w] > res.second)
                res = make_pair(w, count[w]);
        }

        return res.first;
    }
};

```

### Java

```java
class Solution {
    public String mostCommonWord(String paragraph, String[] banned) {
        paragraph += ".";

        Set<String> banset = new HashSet();
        for(String word: banned) banset.add(word);

        Map<String, Integer> count = new HashMap();

        String ans = "";
        int ansfreq = 0;

        StringBuilder word = new StringBuilder();
        for(char c: paragraph.toCharArray()) {
            if(Character.isLetter(c)) {
                word.append(Character.toLowerCase(c));
            }
            else if(word.length() > 0) {
                String finalword = word.toString();
                if(!banset.contains(finalword)) {
                    count.put(finalword, count.getOrDefault(finalword, 0) + 1);
                    if(count.get(finalword) > ansfreq) {
                        ans = finalword;
                        ansfreq = count.get(finalword);
                    }
                }
                word = new StringBuilder();
            }
        }

        return ans;
    }
}
```
Enjoy it!!!
