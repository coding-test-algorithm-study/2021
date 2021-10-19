## Comparable
정렬 가능한 객체가 되려면
1. Comparable 을 implements 한다.
2. int compareTo() 를 Override 한다.

```java
import java.util.*;

// 예제 - 나이에 대한 최소힙
public class Main {

    public static void main(String[] args) {
        PriorityQueue<Person> people = new PriorityQueue<>();

        people.add(new Person(1, 20));
        people.add(new Person(3, 18));
        people.add(new Person(2, 19));

        while (!people.isEmpty()) {
            Person remove = people.remove();
            System.out.println(remove.id + ", " + remove.age);
        }
    }
}

class Person implements Comparable<Person> {

    int id;
    int age;

    public Person(int id, int age) {
        this.id = id;
        this.age = age;
    }

    @Override
    public int compareTo(Person p) {
        return Integer.compare(this.age, p.age);
    }
}
```

## Comparator
```java
import java.util.*;

// 예제 - Id에 대한 최소힙 / Age에 대한 최소힙
public class Main {

    public static void main(String[] args) {
        PriorityQueue<Person> people = new PriorityQueue<>(new AgeComparator());  // Age에 대한 최소힙

        people.add(new Person(1, 20));
        people.add(new Person(3, 18));
        people.add(new Person(2, 19));

        while (!people.isEmpty()) {
            Person remove = people.remove();
            System.out.println(remove.id + ", " + remove.age);
        }
    }
}

class Person {

    int id;
    int age;

    public Person(int id, int age) {
        this.id = id;
        this.age = age;
    }
}

class IdComparator implements Comparator<Person> {

    @Override
    public int compare(Person o1, Person o2) {
        return Integer.compare(o1.id, o2.id);
    }
}

class AgeComparator implements Comparator<Person> {

    @Override
    public int compare(Person o1, Person o2) {
        return Integer.compare(o1.age, o2.age);
    }
}
```
