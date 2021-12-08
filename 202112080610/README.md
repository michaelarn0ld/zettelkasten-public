# Java: On Using Interfaces
Inheritance is a strategy to reuse code based on "this-is-a-that" relationships.
For example, we might have a parent class of fruit. Well an apple is a fruit and
might share some of the same basic properties. In this way, we can create a new
apple class that extends the parent fruit class.

Let's consider another example: let's say we have a video game and three types
of players "HumanPlayer", "BotPlayer", "AgentPlayer" that all extend a parent
"Player" class. The three types of players all move differently and therefore
override the parents "move()" method:
```java
public class Player {
    void move() {
        // code
    }
}

public class HumanPlayer extends Player {
    @Override
    void move() {
        // code
    }
}

public class BotPlayer extends Player {
    @Override
    void move() {
        // code
    }
}

public class AgentPlayer extends Player {
    @Override
    void move() {
        // code
    }
}
```
Since the point of inheritance is to reuse code and there's no reuse here, using
inheritance for this is a bad idea. Instead, let's use an interface:
```java
public interface Player {
    void move(); 
}

public class HumanPlayer implements Player {
    @Override
    void move() {
        // code
    }
}

public class BotPlayer implements Player {
    @Override
    void move() {
        // code
    }
}

public class AgentPlayer implements Player {
    @Override
    void move() {
        // code
    }
}
```

There are three basic rules to follow when using an interface:

1. Use an interface when there are two or more concrete implementations that
solve one problem. Both implementations must enforce the same contract.
1. Use an interface when one concrete implementation solves a problem but there
are possibilities of different implementations that enforce the same contract
1. Use an interface for control testing.


## Related
[202111300552](../202111300552) - Java: Questions on Strings\
[202112021908](../202112021908) - Java: References or Copies?\
[202112061553](../202112061553) - Java: Intro to OOP\
[202112061620](../202112061620) - Java: Class Syntax\
[202112080538](../202112080538) - Java: Questions on Inheritance

## Tags
#java
