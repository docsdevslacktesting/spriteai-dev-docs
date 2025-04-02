{
  "updatedDocumentation": "# Generate Pixel Art

## Introduction

The SpriteAI library provides a powerful tool for generating pixel art from images. This documentation will guide you through the process of using the `generatePixelArt` function to create retro-style pixel art images.

## Usage

To generate pixel art, you can use the `generatePixelArt` function provided by the SpriteAI library. This function takes an image input and generates a pixel art version of the image.

Here's an example of how to use the `generatePixelArt` function:

```javascript
const { generatePixelArt } = require('spriteai');

const originalImage = 'path/to/your/image.jpg';
const pixelArtImage = generatePixelArt(originalImage, {
  scale: 8,
  colors: 16,
  dither: true
});

// Save the pixel art image
await saveImage(pixelArtImage, 'path/to/save/pixel-art.png');
```

The `generatePixelArt` function accepts the following options:

- `scale`: The scaling factor for the pixel art image. A higher value will result in a larger pixel art image.
- `colors`: The number of colors to use in the pixel art image. The library will automatically select the best colors to represent the original image.
- `dither`: A boolean value indicating whether to apply dithering to the pixel art image. Dithering can help improve the visual quality, especially when the number of colors is limited.

## Example

Here's an example of how the `generatePixelArt` function can be used:

```javascript
const { generatePixelArt } = require('spriteai');

const originalImage = 'path/to/your/image.jpg';
const pixelArtImage = generatePixelArt(originalImage, {
  scale: 8,
  colors: 16,
  dither: true
});

// Save the pixel art image
await saveImage(pixelArtImage, 'path/to/save/pixel-art.png');
```

In this example, we load an image from the file system, generate a pixel art version of the image using the `generatePixelArt` function, and then save the resulting pixel art image to a file.

## Conclusion

The SpriteAI library's `generatePixelArt` function provides a convenient way to create retro-style pixel art images from your original images. By adjusting the scale, color count, and dithering options, you can achieve a variety of pixel art styles to fit your needs.
}