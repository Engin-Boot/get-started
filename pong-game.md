# The Pong Game

![pong](images/pong.gif "pong game")

## The Product

We need to develop and release this software for the gaming community.

One way is to code it all in the `main` function.

```C
void main() {
    while(1) {
        //poll the input

        //check collisions, change directions, count points...

        //update UI

        //declare winner and quit(?)
    }
}
```

This has obvious drawbacks:

- As a gaming company, we cannot recruit more people to give new features
demanded by the community
- It grows over time, gradually crossing the limits of understanding

## The task

Cut the implementation into parts.
State the responsibility of each part.
