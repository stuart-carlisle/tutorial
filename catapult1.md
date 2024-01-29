# catapult1
We're going to make a code our catapult to fire when we press the 'A' button

input.onButtonPressed(Button.A, function () {
    if (position == 90) {
        position = 0
    } else {
        position = 90
    }
})
let position = 0
position = 90
basic.showIcon(IconNames.Target)
basic.forever(function () {
    pins.servoWritePin(AnalogPin.P0, position)
    if (position == 0) {
        basic.clearScreen()
        basic.showIcon(IconNames.Skull)
    }
    if (position == 90) {
        basic.clearScreen()
        basic.showIcon(IconNames.Target)
    }
})


## Step 1
Make a new variable and call it ``||variable: position||``. Put a ``||variable: set position To||`` block inside the ``||basic: start||`` block and set it to a value of 90

```blocks
    let position = 0
    position = 90
```

## Step 2
Grab a ``||pins: servo write pin||`` block and put it in the ``||basic: forever||`` loop.
Next grab the ``||variable: position||`` variable and drop it into the appropriate part of the servo write  block you've just added. 
```blocks
    let position = 0
    position = 90
    basic.forever(function () {
        pins.servoWritePin(AnalogPin.P0, position)
    })
```

## Step 3
Next add in a ``||input: button pressed||`` block and make sure it's set to button A. Put in a ``||variable: set position||`` and make sure it's set to 0.
Try it out on the simulator. The servo arm should move a quarter turn when you press button A.
```blocks
    input.onButtonPressed(Button.A, function () {
            position = 0
    })
    let position = 0
    position = 90
    basic.forever(function () {
        pins.servoWritePin(AnalogPin.P0, position)
    })
```

## Step 4
The arm only moves once and stays in the 0 degrees position but we want it to go back and forth on every press. Remove the ``||variable: set position||`` from the forever nd put it to one side. Now use 
an ``||logic: if-else||`` block and drag it in the forever loop. Put the ``||variable: set position to 0||`` in the ``||logic: if part||`` and create another ``||variable: set position to 90||`` in the else part. 
```blocks
input.onButtonPressed(Button.A, function () {
    if true {
        position = 0
    } else {
        position = 90
    }
})
    let position = 0
    position = 90
    basic.forever(function () {
        pins.servoWritePin(AnalogPin.P0, position)
    })
```
## Step 5
Next at the top of the if put in a ``||logic: __ = __||`` block as the condition. Check to see if position = 90. Test it out in the simulator.
Now it should move each time you press the A button.
```blocks
input.onButtonPressed(Button.A, function () {
    if (position == 90) {
        position = 0
    } else {
        position = 90
    }
})
    let position = 0
    position = 90
    basic.forever(function () {
        pins.servoWritePin(AnalogPin.P0, position)
    })
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
where it says **true**.
```blocks
input.onGesture(Gesture.Shake, function () {
    basic.clearScreen()
    option = randint(1, 3)
    if(0==0){
    }else{
    }
})
basic.showNumber(8)
```

## Step 8
Then drag ``||variable: your variable||`` onto the first zero and add
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

## Step 9
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

## Step 10
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

## Step 11
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

## Step 12
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

## Step 13
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

## Step 14
The final step is to download the file and transfer it to your microbit. Ask it a yes-no question and see what it says when you shake it.
Use double sided tape or a loop of tape to attach it to a black cardboard disc with a white centre to make it look like a real magic 8 ball.
Remember to add on the battery pack and stick that on aswell, you could add a small slit to allow you to mount the battery pack on the rear and 
push the battery pack cable through for a cleaner finish.

