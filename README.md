# Advanced sensors

```package
core
radio
microphone
```

```template
basic.forever(function () {
    
})
```

```blocks
basic.forever(function () {
    
})
```
## Step 0 @showDialog
Hello! Today we'll use the Micro:bit sensors again, but with a new twist!
  
This tutorial builds on the knowledge of if-else statements. We strongly recommend you complete the [conditions and statements tutorial](https://makecode.microbit.org/#tutorial:github:craftandcode/conditions-and-statements) first.
## Step 1 @showDialog
Sometimes electronic devices must be able to change their actions based on  readings from sensors.  
  
For example:
- A self-driving car reduces its speed if it senses a pedestrian in its way
- A fire alarm activates when it senses temperatures that are extremely high.  

As you remember, we can get the readings from sensors using round-shaped blocks from the ``||input.input||`` category. Now, let's combine them with ``||logic.if else||`` statements to get fantastic new results!

## Step 2 @showHint
### Example 1: Fire alarm
In this example, the condition inside the``||logic.if||`` block compares readings from ``||input.temperature||`` block with a defined value. 
Let's assemble the code and raise the temperature in the simulator to over 45 degrees Celsius. Can you hear the siren beeping?
```blocks
basic.forever(function () {
    if (input.temperature() > 45) {
        music.playMelody("C C C5 C5 C C C5 C5 ", 120)
    }
})

```
## Step 3 @showHint
### Example 2: Whoosh sounds
In this example, we measure ``||input.acceleration||`` to detect when a device speeds up. If the device stays still, nothing happens, except we stop all the sounds. But as soon as the device is moved with a strong enough force, the condition becomes `true`, and the sound is played.  
Let's assemble this code, download it into the Micro:bit and give it a whoosh!

```blocks
basic.forever(function () {
    if (input.acceleration(Dimension.Strength) > 1200) {
        music.ringTone(input.acceleration(Dimension.Strength))
    } else {
        music.stopAllSounds()
    }
})
```
## Step 4 @showHint
### Example 3: Building level
Construction workers use spirit levels to make sure that the floor of a building is parallel to the ground.
In this example, the Micro:bit tells you the direction in which to tilt to be parallel to the ground. 
Assemble this program and download it to the Micro:bit. Can you create a parallel surface?
```blocks
basic.forever(function () {
    if (input.rotation(Rotation.Roll) > 5) {
        basic.showArrow(ArrowNames.West)
    } else if (input.rotation(Rotation.Roll) < -5) {
        basic.showArrow(ArrowNames.East)
    } else {
        basic.showIcon(IconNames.Yes)
    }
})

```

## Step 5 @showHint
### Now it's your turn!
We've prepared a challenge for you! Use ``||logic.if else||`` statements and ``||input.light level||`` readings to tell whether it's day or night!
- If the light level is above 100, it's day
- If the light level is below 100, it's night

## Step 6 @showDialog
### Answers: Now it's your turn! 
Your code might be something like this:

```blocks
basic.forever(function () {
    if (input.lightLevel() > 100) {
        basic.showLeds(`
            # . # . #
            . # # # .
            # # . # #
            . # # # .
            # . # . #
            `)
    } else {
        basic.clearScreen()
    }
})
```
## Step 6
Today you've completed four cool projects and learned to make the Micro:bit react to changes in the sensor readings! You're a star!
