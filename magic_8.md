# Magic 8 Ball
We're going to make a magic 8 bal that when shookanswers your question with a generic answer


## Step 1
To start, we need the 8 number to be seen at the start. Use an ``||basic: onStart||`` block from the basics tab
display a number **8** on the screen using ``||basic: showNumber||``
```blocks
    basic.showNumber(8)
```

## Step 2
Grab an ``||input: onShake||`` block from the ``||input: Input||`` tab. This will allow to shake the Magic 8 Ball to reveal it's answer.
```blocks
    input.onGesture(Gesture.Shake, function () {

    })
    basic.showNumber(8)
```

## Step 3
Now select a ``||basic: clearScreen||`` block and place it inside the ``||input: onShake||`` block to remove the 8 from the screen
```blocks
    input.onGesture(Gesture.Shake, function () {
        basic.clearScreen()
    })
    basic.showNumber(8)
```

## Step 4
Next, we need to make a variable to store a random number into.  Go to the ``||variable: Variable||`` tab and create a ``||variable: new Variable||``. 
Give it a name such as **option** but you can choose any name and set it to a value of **0**. Place it underneath the clearScreen command inside your ``||input: onShake||`` block.
```blocks

input.onGesture(Gesture.Shake, function() {
clearScreen()
option=0
})
    basic.showNumber(8)
```
## Step 5
Now we need the variable to be set randomly.  Use the ``||math: pickRandom||`` block and replace the zero in your set variable statement
from the last step.  Finally, change the value so that the microbit randomly chooses a number between 1 and 3.
```blocks
input.onGesture(Gesture.Shake, function () {
    clearScreen()
    number = randint(1, 4)
})
basic.showNumber(8)
```

## Step 7
```blocks
input.onGesture(Gesture.Shake, function () {
    basic.clearScreen()
    number = randint(1, 4)
    if (number == 4) {
        music._playDefaultBackground(music.builtInPlayableMelody(Melodies.Entertainer), music.PlaybackMode.InBackground)
        basic.showString("Yes, of course")
    } else if (number == 3) {
        music._playDefaultBackground(music.builtInPlayableMelody(Melodies.Funeral), music.PlaybackMode.InBackground)
        basic.showString("Hell No!")
    } else if (number == 2) {
        music._playDefaultBackground(music.builtInPlayableMelody(Melodies.Prelude), music.PlaybackMode.InBackground)
        basic.showString("That's highly likely")
    } else {
        music._playDefaultBackground(music.builtInPlayableMelody(Melodies.Wawawawaa), music.PlaybackMode.InBackground)
        basic.showString("Not with your luck")
    }
    basic.showNumber(8)
})
let number = 0
basic.showNumber(8)

```