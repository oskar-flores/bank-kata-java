# Bank Kata

Your bank is tired of its mainframe COBOL accounting
software and they hired both of you for a greenfield project in your
favorite programming language!

Your task is to show them that your TDD-full and your new-age programming language can cope with good ole’ COBOL!

## Requirements

Your code should fulfill the following requirements:

**Scenario** : Can depose and withdraw money on my account

```
Given a client makes a deposit of 1000€ on 10-01-2012
  And a deposit of 2000€ on 13-01-2012
  And a withdrawal of 500€ on 14-01-2012
When she prints her bank statement
Then she would see
Date       || Credit    || Debit  || Balance
14/01/2012 ||           || 500.00 || 2500.00
13/01/2012 || 2000.00   ||        || 3000.00
10/01/2012 || 1000.00   ||        || 1000.00```
```
**Scenario** : Can depose money on my account with different currencies

```
Given a client makes a deposit of 1000€ on 10-01-2012
And a deposit of 2000€ on 13-01-2012
And a withdrawal of 500€ on 14-01-2012
When she prints her bank statement
Then she would see
Date       || Credit    || Debit  || Balance
14/01/2012 ||           || 500.00 || 2500.00
13/01/2012 || 2000.00   ||        || 3000.00
10/01/2012 || 1000.00   ||        || 1000.00`
```


**Scenario** : Can withdraw money on my account with different currencies

```Given the exchange rate EUR to USD is 1.206
Given a client makes a deposit of 1000€ on 10-01-2012
And a withdrawal of 500$ on 14-01-2012
When she prints her bank statement
Then she would see
Date       || Credit    || Debit  || Balance
14/01/2012 ||           || 500.00 || 2500.00
13/01/2012 || 2000.00   ||        || 3000.00
10/01/2012 || 1000.00   ||        || 1000.00`
```

## Rules
When creating the bank statement, you should use the following rules:
## The Rules

1. One level of indentation per method

    ```java
    class Board {
    //Baad , baad
        public String board() {
            StringBuilder buf = new StringBuilder();
    
            // 0
            for (int i = 0; i < 10; i++) {
                // 1
                for (int j = 0; j < 10; j++) {
                    // 2
                    buf.append(data[i][j]);
                }
                buf.append("\n");
            }
    
            return buf.toString();
        }
    }
    ```

2. Don’t use the ELSE keyword
3. Wrap all primitives and String and Json Object

    ```java
    cannot use string, or int or json object as parameter
    ```

4. First class collections

    ```java
    Any class that contains a collection should contain no other member variables. If you have a set of elements and want to manipulate them, create a class that is dedicated for this set.
    
    Each collection gets wrapped in its own class, 
    so now behaviors related to the collection have a home (e.g. filter methods, applying a rule to each element).
    
    hint: think as a inMEmory Repository
    ```

5. One dot per line

    ```
    Law Of Demeter : 
    An Object should not have the knowledge on the inner details of the objects it manipulates
    //bad bad bad
    car.engine.start()
    ```

6. Don’t abbreviate

    ```
     Method names have to have 1-2 words
    ```

7. Keep all entities small (50 lines)

    ```
    This means no class over 50 lines and no package over 10 files.
    ```

8. No classes with more than two instance variables

    ```
    In this case, two is a very arbitrary value, but ths is the example :
    
    Each Class has only 2 variables, no more!
    ```

   ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/bc94728d-9812-463f-9283-c1e58232130e/Untitled.png)

9. No getters/setters/properties (account.data is forbidden)

```
It is okay to use accessors to get the state of an object, 
as long as you don’t use the result to make decisions outside the object. 
Any decisions based entirely upon the state of one object should be made inside the object itself.

That is why getters/setters are often considered evil. 
Then again, they violate the Open/Closed Principle.

/ Game
private int score;

public void setScore(int score) {
    this.score = score;
}

public int getScore() {
    return score;
}

// Usage
game.setScore(game.getScore() + ENEMY_DESTROYED_SCORE);
```



## Bonus

Test skeleton is already provided.

just run ```./gradlew clean test```