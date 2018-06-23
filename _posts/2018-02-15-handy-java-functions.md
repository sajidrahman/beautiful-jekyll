---
layout: post
title: Miscellaneous and Handy Java Functions
share-img: /img/misc.jpg
tags: [Java, Miscellaneous, functions]
---
#### Object Ordering/Comparing:

A ``List l`` can be sorted as follows:
``Collections.sort(l)``. If the ``List`` consists of built-in class objects, e.g. ``String, Integer, Long, Date, Character, File`` etc., then the objects will be sorted in a way of _natural_ ordering of that class. But for objects from custom classes, our class needs to either implement ``Comparable`` interface or it can implement ``Comparator`` interface to provide a custom comparator for ``Collections.sort(list, comparator)`` method. The following example is borrowed from [Oracle's tutorial](https://docs.oracle.com/javase/tutorial/collections/interfaces/order.html) page.
```java

import java.util.*;
public class EmpSort {
  //we can either define a comparator here
    static final Comparator<Employee> SENIORITY_ORDER =
                                        new Comparator<Employee>() {
            public int compare(Employee e1, Employee e2) {
                return e2.hireDate().compareTo(e1.hireDate());
            }
    };

    // Employee database
    static final Collection<Employee> employees = ... ;

    public static void main(String[] args) {
        List<Employee> employeeList = new ArrayList<Employee>(employees);
        //Collections.sort(employeeList,  SENIORITY_ORDER);
        // Or we can define comparator in-line with the sort method, as shown below
        @Override
        Collections.sort(employeeList, new Comparator<Employee>() {
            public int compare(Employee e1, Employee e2) {
                return e2.hireDate().compareTo(e1.hireDate());
            }
    });
        System.out.println(employeeList);
    }
}
```
