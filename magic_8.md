# Magic 8 Ball
We're going to make a magic 8 bal that when shookanswers your question with a generic answer


## Step 1
To start, bin the ``||basic: Forever||`` block by dragging it across to the menu and letting go. 
Now we need the 8 number to be seen at the start. Inside the ``||basic: on start||`` block
``||basic: show number||`` to display a number **8** on the screen
```blocks
    basic.showNumber(8)
```

## Step 2
Grab an ``||input: on shake||`` block from the ``||input: Input||`` tab. Drag into the open space anywhere in the window. This will allow to shake the Magic 8 Ball to reveal it's answer.
```blocks
    input.onGesture(Gesture.Shake, function () {

    })
    basic.showNumber(8)
```

## Step 3
Now select a ``||basic: clear screen||`` block and place it inside the ``||input: on shake||`` block to remove the 8 from the screen when the microbit is shook.
```blocks
    input.onGesture(Gesture.Shake, function () {
        basic.clearScreen()
    })
    basic.showNumber(8)
```

## Step 4
Next, we need to make a variable to store a random number into.  Go to the ``||variable: Variables||`` tab and ``||variable: make a new variable||``. 
Type in a name such as **option** (you can choose any name you wish for a variable though). Drag across the ``||variable: set variable to 0||`` block and place it underneath the ``||basic: clear screen``|| block inside your ``||input: on shake||`` block.
```blocks
input.onGesture(Gesture.Shake, function() {
basic.clearScreen()
option=0
})
    basic.showNumber(8)
```
## Step 5
Change the variable from zero to a random number. Use the ``||math: pick random||`` block and drag it to the zero in your ``||variable: set variable||`` statement
from the last step.  Finally, change the value so that the microbit randomly chooses a number between 1 and 3.
```blocks
input.onGesture(Gesture.Shake, function () {
    basic.clearScreen()
    option = randint(1, 3)
})
basic.showNumber(8)
```

## Step 6
We now need to give a different response for each random number. Use an ``||logic: if-else||`` block below the 
random number you just defined
```blocks
input.onGesture(Gesture.Shake, function () {
    basic.clearScreen()
    option = randint(1, 3)
    if(true){
    }else{
    }
})
basic.showNumber(8)
```
## Step 7
Add a comparison operator, the ``||logic: 0 = 0||`` type and drop it into the if block
where it says **true**. then drag into the first zero ``||variable: your variable||`` and add
a 3 in place of the second zero to see if your random number is equal to 3.
```blocks
input.onGesture(Gesture.Shake, function () {
    basic.clearScreen()
    option = randint(1, 3)
    if(option==3){
    }else{
    }
})
basic.showNumber(8)
```

## Step 8
Use ``||basic: showString||`` to show a positive answer like **'Yes'**
drop it inside the ``||logic: if block||``.
```blocks
input.onGesture(Gesture.Shake, function () {
    basic.clearScreen()
    option = randint(1, 3)
    if(option==3){
        basic.showString("Yes!")
    }else{
    }
})
basic.showNumber(8)
```

## Step 9
As we have 3 options for our random number 1, 2 or 3 we need another two possibilities on the if-else block.
Click the plus button on the bottom of the ``||logic: if-else||`` block to get another option and add in code to see
if the random number (your variable) is 2, show a string that says a negative answer like **'No!'**
```blocks
input.onGesture(Gesture.Shake, function () {
    basic.clearScreen()
    option = randint(1, 3)
    if(option==3){
        basic.showString("Yes!")
    }else if(option==2){
        basic.showString("No!")
    }else{
    }
})
basic.showNumber(8)
```

## Step 10
In the else part of the if-else block add a maybe response like **'maybe'**
```blocks
input.onGesture(Gesture.Shake, function () {
    basic.clearScreen()
    option = randint(1, 3)
    if(option==3){
        basic.showString("Yes!")
    }else if(option==2){
        basic.showString("No!")
    }else{
        basic.showString("Maybe!")
    }
})
basic.showNumber(8)
```

## Step 11
Now add code **after** the if-else block but still inside the ``||input: onShake||`` block to set the back to the number **8** like we had at the start
using ``||basic: showNumber||`` block again.
```blocks
input.onGesture(Gesture.Shake, function () {
    basic.clearScreen()
    option = randint(1, 3)
    if(option==3){
        basic.showString("Yes!")
    }else if(option==2){
        basic.showString("No!")
    }else{
        basic.showString("Maybe!")
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
    basic.clearScreen()
    option = randint(1, 3)
    if(option==3){
        music._playDefaultBackground(music.builtInPlayableMelody(Melodies.Entertainer), music.PlaybackMode.InBackground)
        basic.showString("Yes!")
    }else if(option==2){
        music._playDefaultBackground(music.builtInPlayableMelody(Melodies.Funeral), music.PlaybackMode.InBackground)
        basic.showString("No!")
    }else{
        music._playDefaultBackground(music.builtInPlayableMelody(Melodies.Prelude), music.PlaybackMode.InBackground)
        basic.showString("Maybe!")
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