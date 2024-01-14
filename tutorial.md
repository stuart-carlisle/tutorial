```package
microturtle=github:microsoft/pxt-microturtle
```

# tutorial
## step 1

add code to display a **smiley**

```blocks
basic.showString(":)")
```

## step 2

add code to display a **frown**

```blocks
basic.showString(":)")
basic.showString(":(")
```

## step 3

try it out on your microbit!

<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>

## step 4

Click on the ``||variables:Variables||`` category in the Toolbox again. You'll notice that there are some new blocks that have appeared. Drag a ``||variables:set hand||`` block into the ``||input:on shake||`` block. We'll start our Rock Paper Scissors game when we shake 👋 our micro:bit.

```blocks
let hand = 0;
input.onGesture(Gesture.Shake, function() {
    hand = 0
})
```