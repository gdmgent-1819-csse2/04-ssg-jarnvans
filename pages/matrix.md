---
layout: default
title: Documentation - Matrices
permalink: ./docs/matrices/
---

## Matrices

### Creating a matrix

To create a new matrix you have to do the following

first:

```js
  import Matrix2 from '../../../Library/Math/Matrix2.js'
```

then:

```js
  const matrixArray = [
    1, 6,
    3, 8,
  ]

  const matrix = new Matrix2(matrixArray)
```


When we create a matrix, the code below is executed

```js
  constructor(items){
    this.items = items || [
      0, 0,
      0, 0,
    ]
  }

```

### Matrix operations
Once you created a matrix you can start using functions.

Here's how to call a function

```js
  matrix.add(secondMatrix)
```

**add(m2)**

When you call the **add()** function you can add 2 matrices together.

```js
  add(secondMatrix)
  {
    const originalMatrix = this.items
    this.items = [
      originalMatrix[0] + secondMatrix[0], originalMatrix[1] + secondMatrix[1],
      originalMatrix[2] + secondMatrix[2], originalMatrix[3] + secondMatrix[3]
    ]
  }
```

**sub(m2)**

The **sub()** function subtracts 2 matrices.

```js
  sub(secondMatrix)
  {
    const originalMatrix = this.items
    this.items = [
      originalMatrix[0] - secondMatrix[0], originalMatrix[1] - secondMatrix[1],
      originalMatrix[2] - secondMatrix[2], originalMatrix[3] - secondMatrix[3]
    ]
  }
```

**mul(m2)**

When we call this function we get the product of 2 matrices.

```js
  mul(secondMatrix)
  {
    const originalMatrix = this.items
    const productMatrix = []
    productMatrix[0] = originalMatrix[0] * secondMatrix[0] + originalMatrix[1] * secondMatrix[2]
    productMatrix[1] = originalMatrix[0] * secondMatrix[1] + originalMatrix[1] * secondMatrix[3]
    productMatrix[2] = originalMatrix[2] * secondMatrix[0] + originalMatrix[3] * secondMatrix[2]
    productMatrix[3] = originalMatrix[2] * secondMatrix[1] + originalMatrix[3] * secondMatrix[3]

    this.items = productMatrix
  }
```

**rot(α)**

This function rotates the matrix.

```js
  rot(α) {
    α *= Math.PI / 180
    const cos = Math.cos(α)
    const sin = Math.sin(α)
    const originalMatrix = this.items
    const rotationMatrix = [
        cos, -sin,
        sin, cos,
    ]
    this.items = rotationMatrix
    this.mul(originalMatrix);
  }
```




