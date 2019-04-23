---
layout: default
title: Documentation - Clock
permalink: ./docs/clock/
---

## Clock

Here we will create a very simple analog clock using vectors, here's what we will get.

```js

  updateCanvasHandler(event) {
    console.log('updateCanvas')
    this.clearData()

    // White point in the middle
    this.data.positions.push(0, 0)
    this.data.colors.push(...this.colors.white)

    const v = new Vector2(0.6, 0)
    this.data.positions.push(v.x, v.y)
    this.data.colors.push(...this.colors.white)

    for(let i = 0; i < 12; i++){
        v.rot(30);
        this.data.positions.push(v.x, v.y)
        this.data.colors.push(...this.colors.white)
    } 

    const date = new Date()

    let seconds = date.getSeconds()
    let minutes = date.getMinutes()
    let hours = date.getHours()

    let secondsVector = new Vector2(0, 0.5)
    secondsVector.rot(seconds * -6)
    this.data.positions.push(secondsVector.x, secondsVector.y)
    this.data.colors.push(...this.colors.red)
    let minutesVector = new Vector2(0, 0.6)
    minutesVector.rot(minutes * -6)
    this.data.positions.push(minutesVector.x, minutesVector.y)
    this.data.colors.push(...this.colors.yellow)
    let hoursVector = new Vector2(0, 0.4)
    hoursVector.rot(hours * -6)
    this.data.positions.push(hoursVector.x, hoursVector.y)
    this.data.colors.push(...this.colors.green)

    this.drawScene()
  }

```

### Creating the clock

Simple. Just clear all the data with this function

```js

  this.clearData()

```

Now we'll create our white point in the middle

```js

  this.data.positions.push(0, 0)
  this.data.colors.push(...this.colors.white)

```

Now we'll create a new vector for the 12 points that represent the hours. We are going to rotate this vector so we get 12 points.

```js

  const v = new Vector2(0.6, 0)
  this.data.positions.push(v.x, v.y)
  this.data.colors.push(...this.colors.white)

  for(let i = 0; i < 12; i++){
      v.rot(30);
      this.data.positions.push(v.x, v.y)
      this.data.colors.push(...this.colors.white)
  } 

```

### Setting the time

Here we will see how to get the current time and how to convert it to vectors.

```js
  
  const date = new Date()

  let seconds = date.getSeconds()
  let minutes = date.getMinutes()
  let hours = date.getHours()

  let secondsVector = new Vector2(0, 0.5)
  secondsVector.rot(seconds * -6)
  this.data.positions.push(secondsVector.x, secondsVector.y)
  this.data.colors.push(...this.colors.red)
  let minutesVector = new Vector2(0, 0.6)
  minutesVector.rot(minutes * -6)
  this.data.positions.push(minutesVector.x, minutesVector.y)
  this.data.colors.push(...this.colors.yellow)
  let hoursVector = new Vector2(0, 0.4)
  hoursVector.rot(hours * -6)
  this.data.positions.push(hoursVector.x, hoursVector.y)
  this.data.colors.push(...this.colors.green)

```

### Draw the time

The only thing left to do is draw our clock on the screen.

```js
  
  this.drawScene()

```

