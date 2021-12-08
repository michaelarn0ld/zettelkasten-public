# Java: Questions on Inheritance
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

public class Game {

    private Player[] players;

    // Omitting all initialization and non-essential details.

    public void movePlayers() {
        for (Player player : players) {
            player.move();
        }
    }
}
```

Q: Even though technically a BotPlayer and AgentPlayer are different classes, is
the reason they can both be included in Player[] because they both inherit from
the Player class (they are children/subclasses of Player)?

A:


## Related
[202111300552](../202111300552) - Java: Questions on Strings
[202112021908](../202112021908) - Java: References or Copies?
[202112061553](../202112061553) - Java: Intro to OOP
[202112061620](../202112061620) - Java: Class Syntax


## Tags
#java
