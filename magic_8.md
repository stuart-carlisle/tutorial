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
    option = randint(1, 3)
})
basic.showNumber(8)
```

## Step 6
We now need to give a different response for each random number. Use an ``||logic: if-else||`` block below the 
random number you just defined
```blocks
input.onGesture(Gesture.Shake, function () {
    clearScreen()
    option = randint(1, 3)
    if(true){
    }else{
    }
})
basic.showNumber(8)
```
## Step 7
Add a ``||logic: Comparison Operator||`` of the **'='** type into the if block
then use the ``||variable: option||`` or whatever you named your variable at the start and 
set to see if option is equal to 3 
```blocks
input.onGesture(Gesture.Shake, function () {
    clearScreen()
    option = randint(1, 3)
    if(option==3){
    }else{
    }
})
basic.showNumber(8)
```

## Step 8
If it is **'3'** then write a string inside the **'if'** part of the if-else block
Use ``||basic: showString||`` to show a positive message like "Yes, of course"
```blocks
input.onGesture(Gesture.Shake, function () {
    clearScreen()
    option = randint(1, 3)
    if(option==3){
        basic.showString("Yes, of course")
    }else{
    }
})
basic.showNumber(8)
```

## Step 9
As we have 3 options for our random number 1, 2 or 3 we need another two possibilities on the if-else block.
Click the plus button on the bottom of the ``||logic: if-else||`` block to get another option and add in code to see
if the random number (your variable) is 2, show a string that says a negative message like **'No way Jose'**
```blocks
input.onGesture(Gesture.Shake, function () {
    clearScreen()
    option = randint(1, 3)
    if(option==3){
        basic.showString("Yes, of course")
    }else if(option==2){
        basic.showString("No way Jose!")
    }else{
    }
})
basic.showNumber(8)
```

## Step 10
In the else part of the if-else block add a maybe response like 'Could happen'
```blocks
input.onGesture(Gesture.Shake, function () {
    clearScreen()
    option = randint(1, 3)
    if(option==3){
        basic.showString("Yes, of course")
    }else if(option==2){
        basic.showString("No way Jose!")
    }else{
        basic.showString("Could happen")
    }
})
basic.showNumber(8)
```

## Step 11
Now add code **after** the if-else block but still inside the ``||input: onShake||`` block to set the back to the number 8 like we had at the start
using ``||basic: showNumber||`` block again.
```blocks
input.onGesture(Gesture.Shake, function () {
    clearScreen()
    option = randint(1, 3)
    if(option==3){
        basic.showString("Yes, of course")
    }else if(option==2){
        basic.showString("No way Jose!")
    }else{
        basic.showString("Could happen")
    }
    basic.showNumber(8)
})
basic.showNumber(8)
```

## Step 12
Check the simulator, you should now have a working magic 8 ball.  Finally to make it more fun
Add in some melodies that play for each option where you put your response string. Use ``||music: play||`` in the advanced section of the 
music tab.  Keep it as play in the background. Choose an appropriate sound.


```blocks
input.onGesture(Gesture.Shake, function () {
    clearScreen()
    option = randint(1, 3)
    if(option==3){
        music._playDefaultBackground(music.builtInPlayableMelody(Melodies.Entertainer), music.PlaybackMode.InBackground)
        basic.showString("Yes, of course")
    }else if(option==2){
        music._playDefaultBackground(music.builtInPlayableMelody(Melodies.Funeral), music.PlaybackMode.InBackground)
        basic.showString("No way Jose!")
    }else{
        music._playDefaultBackground(music.builtInPlayableMelody(Melodies.Prelude), music.PlaybackMode.InBackground)
        basic.showString("Could happen")
    }
    basic.showNumber(8)
})
basic.showNumber(8)
```

## Step 13
The final step is to download the file and transfer it to your microbit. Ask it a yes-no question and see what it says when you shake it.
Use double sided tape or a loop of tape to attach it to a black cardboard disc with a white centre to make it look like a real magic 8 ball.
Remember to add on the battery pack and stick that on aswell, you could add a small slit to allow you to mount the battery pack on the rear and 
push the battery pack cable through for a cleaner finish.