---
layout: post
title: Tech Prep Journal
share-img: /img/misc.jpg
tags: [Interview, Miscellaneous, functions]
---


1. **Finding palindrome made easy**: In investigating whether a given string is a palindrome, we really just need to know _there isn’t more than one character that appears an odd number of times, i.e. unpaired_. What if we only track the characters that appear an odd number of times? Is there a data structure even simpler than a hash map we could use? We could use a `hash set`, adding and removing characters as we look through the input string, so the hash set always only holds the characters that appear an odd number of times.

```java

import java.util.Set;
import java.util.HashSet;

public static boolean hasPalindromePermutation(String theString) {

    // track characters we've seen an odd number of times
    Set<Character> unpairedCharacters = new HashSet<>();

    for (char c : theString.toCharArray()) {
        if (unpairedCharacters.contains(c)) {
            unpairedCharacters.remove(c);
        } else {
            unpairedCharacters.add(c);
        }
    }

    // the string has a palindrome permutation if it
    // has one or zero characters without a pair
    return unpairedCharacters.size() <= 1;
}
```
