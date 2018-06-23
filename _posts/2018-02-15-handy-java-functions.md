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
        System.out.println(e);
    }
}
```
0. Make sure you have homebrew installed in your machine, otherwise follow instrunctions at [brew.sh](https://brew.sh/).
1. Open terminal, run `brew install sonar`. Assuming brew installs SonarQube successfully, take a look at the last line of the terminal where the SonarQube location is printed. In my case it is `/usr/local/Cellar/sonarqube/7.1`.
2. Now run `brew install sonar-scanner` (N.B. sonar-runner is no longer available, it's replaced by sonar-scanner).
3. After installation is complete, run the following commands consecutively:
 `export SONAR_HOME=/usr/local/Cellar/sonar-scanner/3.2.0.1227/libexec
  export SONAR=$SONAR_HOME/bin
  export PATH=$SONAR:$PATH`
  [TODO: exporting path in this way will work for the current session of terminal, for permanent use, I need to transfer these path variables to .bashrc file.]
4. Now we can run SonarQube from terminal by issuing this command `/usr/local/opt/sonarqube/bin/sonar console`.
5. Go to http://localhost:9000/ to view the main page of SonarQube. Use this credentials (username: admin, password: admin) to login.

References (deprecated a bit):
- [How to Setup SonarQube on Mac Part-1](http://zafercelaloglu.blogspot.com/2014/07/how-to-setup-sonar-on-mac-part-1.html)
- [Install Sonar Locally on OSX ](http://www.managerjs.com/blog/2015/11/install-sonar-locally-on-osx-and-analyze-a-javascript-project/)
