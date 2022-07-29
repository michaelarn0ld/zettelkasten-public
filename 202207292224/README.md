# Sets of Objects - Java

## Default Behavior
If you do not override `hashCode()` for an object in Java, then the default
behavior of the below snippet:
```
public class App {
    public static void main(String[] args) {
        Set<Person> personSet = new HashSet<>();
        Person person1 = new Person("Michael", 23);
        Person person2 = new Person("Michael", 23);
        Person person3 = new Person("Michael", 23);
        personSet.add(person1);
        personSet.add(person2);
        personSet.add(person3);
        personSet.forEach(System.out::println);
    }
}
```
Would be
```
Person{name='Michael', age=23}
Person{name='Michael', age=23}
Person{name='Michael', age=23}
```

If we print out the hash codes for each of the 3 `Person` objects, we get:
```
Person 1: 431687835
Person 2: 2109957412
Person 3: 901506536
```

## Modifying Hashcode
However, if you override the `hashCode()` method to return a hash based on the
data contains within the members of the class then for the same snippet, you will
get:
```
Person{name='Michael', age=23}
```

If we print out the hash codes for each of the 3 `Person` objects now, we get:
```
Person 1: -1610628431
Person 2: -1610628431
Person 3: -1610628431
```

## Tags
#hashing #java
