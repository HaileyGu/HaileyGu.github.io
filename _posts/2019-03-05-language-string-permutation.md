---
layout: post
title:  "[Languages] String Permutation(cpp/java)"
date:   2019-03-05 21:00:00
categories: ProgrammingLanguages
tags: ProgrammingLanguages C++ Java
author: Hailey Gu
---

* content
{:toc}

## StringBuilder example

[link](https://www.interviewcake.com/question/cpp/recursive-string-permutations?utm_source=weekly_email&utm_source=drip&utm_campaign=weekly_email&utm_campaign=Interview%20Cake%20Weekly%20Problem%20%23233:%20Recursive%20String%20Permutations&utm_medium=email&utm_medium=email){:target="_blank"}

### C++
```c++
#include <iostream>
#include <string>
#include <unordered_set>

// C++11 lest unit testing framework
#include "lest.hpp"

using namespace std;

unordered_set<string> getPermutations(const string& inputString)
{
    unordered_set<string> permutations;

    // base case
    if (inputString.length() <= 1) {
        permutations.insert(inputString);
        return permutations;
    }

    string allCharsExceptLast = inputString.substr(0, inputString.length() - 1);
    char lastChar = inputString[inputString.length() - 1];

    // recursive call: get all possible permutations for all chars except last
    const auto permutationsOfAllCharsExceptLast = getPermutations(allCharsExceptLast);

    // put the last char in all possible positions for each of the above permutations
    for (const string& permutationOfAllCharsExceptLast : permutationsOfAllCharsExceptLast) {
        for (size_t position = 0; position <= allCharsExceptLast.length(); ++position) {
            string permutation = permutationOfAllCharsExceptLast.substr(0, position)
                    + lastChar + permutationOfAllCharsExceptLast.substr(position);
            permutations.insert(permutation);
        }
    }

    return permutations;
}


// tests

const lest::test tests[] = {
    CASE("empty string") {
        const unordered_set<string> expected {""};
        auto actual = getPermutations("");
        EXPECT(actual == expected);
    },
    CASE("one character string") {
        const unordered_set<string> expected {"a"};
        auto actual = getPermutations("a");
        EXPECT(actual == expected);
    },
    CASE("two character string") {
        const unordered_set<string> expected {"ab", "ba"};
        auto actual = getPermutations("ab");
        EXPECT(actual == expected);
    },
    CASE("three character string") {
        const unordered_set<string> expected {"abc", "acb", "bac", "bca", "cab", "cba"};
        auto actual = getPermutations("abc");
        EXPECT(actual == expected);
    }
};

int main(int argc, char** argv)
{
    return lest::run(tests, argc, argv);
}

```

### Java

```java
import java.util.Arrays;
import java.util.Set;
import java.util.HashSet;
import java.util.Collections;

import org.junit.Test;
import org.junit.runner.JUnitCore;
import org.junit.runner.Result;
import org.junit.runner.notification.Failure;

import static org.junit.Assert.*;

public class Solution {

public static Set<String> getPermutations(String inputString) {

    // base case
    if (inputString.length() <= 1) {
        return new HashSet<>(Collections.singletonList(inputString));
    }

    String allCharsExceptLast = inputString.substring(0, inputString.length() - 1);
    char lastChar = inputString.charAt(inputString.length() - 1);

    // recursive call: get all possible permutations for all chars except last
    Set<String> permutationsOfAllCharsExceptLast = getPermutations(allCharsExceptLast);

    // put the last char in all possible positions for each of the above permutations
    Set<String> permutations = new HashSet<>();
    for (String permutationOfAllCharsExceptLast : permutationsOfAllCharsExceptLast) {
        for (int position = 0; position <= allCharsExceptLast.length(); position++) {
            String permutation = permutationOfAllCharsExceptLast.substring(0, position) + lastChar
                + permutationOfAllCharsExceptLast.substring(position);
            permutations.add(permutation);
        }
    }

    return permutations;
}


    // tests

    @Test
    public void emptyStringTest() {
        final Set<String> expected = new HashSet<>(Arrays.asList(""));
        final Set<String> actual = getPermutations("");
        assertEquals(expected, actual);
    }

    @Test
    public void oneCharacterStringTest() {
        final Set<String> expected = new HashSet<>(Arrays.asList("a"));
        final Set<String> actual = getPermutations("a");
        assertEquals(expected, actual);
    }

    @Test
    public void twoCharacterStringTest() {
        final Set<String> expected = new HashSet<>(Arrays.asList("ab", "ba"));
        final Set<String> actual = getPermutations("ab");
        assertEquals(expected, actual);
    }

    @Test
    public void threeCharacterStringTest() {
        final Set<String> expected = new HashSet<>(Arrays.asList("abc", "acb", "bac", "bca",
                                                                 "cab", "cba"));
        final Set<String> actual = getPermutations("abc");
        assertEquals(expected, actual);
    }

    public static void main(String[] args) {
        Result result = JUnitCore.runClasses(Solution.class);
        for (Failure failure : result.getFailures()) {
            System.out.println(failure.toString());
        }
        if (result.wasSuccessful()) {
            System.out.println("All tests passed.");
        }
    }
}
```
Enjoy it!!!
