# Generate Pixel Art

## Overview

The `generatePixelArt` function is used to generate pixel art from an input image. It takes an image file as input and generates a pixel art representation of the image.

## Usage

To use the `generatePixelArt` function, you can import it from the `spriteAI` module and call it with an input image file:

```javascript
const { generatePixelArt } = require('spriteAI');

generatePixelArt('input_image.jpg')
  .then(pixelArtData => {
    // Process the generated pixel art data
    console.log(pixelArtData);
  })
  .catch(error => {
    console.error('Error generating pixel art:', error);
  });
```

The `generatePixelArt` function returns a Promise that resolves with the generated pixel art data. The data is a 2D array representing the pixel art image, where each element in the array represents a pixel and contains the RGB color values.

## Configuration

You can customize the behavior of the `generatePixelArt` function by passing an optional configuration object as the second argument:

```javascript
generatePixelArt('input_image.jpg', {
  pixelSize: 10,
  palette: ['#FF0000', '#00FF00', '#0000FF']
})
  .then(pixelArtData => {
    // Process the generated pixel art data
    console.log(pixelArtData);
  })
  .catch(error => {
    console.error('Error generating pixel art:', error);
  });
```

The available configuration options are:

- `pixelSize`: The size of each pixel in the generated pixel art (default is 5 pixels).
- `palette`: An array of hexadecimal color codes to use in the pixel art (default is a set of 16 colors).

## Examples

You can find examples of using the `generatePixelArt` function in the `examples` directory of the `spriteAI` package.
