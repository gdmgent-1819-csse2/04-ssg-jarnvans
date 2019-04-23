---
layout: default
title: Vectors
permalink: ./docs/vectors/
---

## Vectors

### Creating a vector

To create a new vector you have to do the following

first:

```js
  import Vector2 from '../../../Library/Math/Vector2.js'
```

then:

```js
  const newVector = new Vector2(3, 6)
```


When we create a vector, the code below is executed

```js
  constructor(x, y) 
  {
    this.x = Number(x) || 0
    this.y = Number(y) || 0
  }

```

### Vector operations
Once you created a vector you can start using functions.

Here's how to call a function

```js
  newVector.add(secondVector)
  newVector.scalar(2)
```

**add(v2)**

When you call the **add()** function you can add 2 vectors together.

```js
  add(secondVector) 
  {
    this.x += secondVector.x
    this.y += secondVector.y
  }
```

**sub(v2)**

The **sub()** function subtracts 2 vectors.

```js
  sub(secondVector) 
  {
    this.x -= secondVector.x
    this.y -= secondVector.y
  }
```

**scalar(a)**

This function multiplies a vector by a scalar.

```js
  scalar(scalarNumber) 
  {
    this.x *= scalarNumber
    this.y *= scalarNumber
  }
```

**dot(v2)**

When we call this function we get the product of 2 vectors.

```js
  dot(secondVector) {
    return this.x * secondVector.x + this.y * secondVector.y
  }
```

**norm()**

This function gives us the length of the vector.

```js
  norm() 
  {
    return Math.sqrt(Math.pow(this.x, 2) + Math.pow(this.y, 2));
  }
```

**rot(α)**

this function rotates the vector.

```js
  rot(α) {
    const matrix = new Matrix2([
      this.x, 0, 
      this.y, 0
    ])
    matrix.rot(α)
    console.log(matrix)
    this.x = matrix.items[0]
    this.y = matrix.items[2]
  }
```




