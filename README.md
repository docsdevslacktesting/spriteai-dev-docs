# SpriteAI Documentation

## Overview

SpriteAI is a Node.js library that leverages the DALL-E 3 language model from OpenAI to generate character spritesheets and environment sprites for use in games and other interactive applications. This library provides a simple API to create customized sprite assets based on text descriptions.

## Key Features

- Automatically generate character spritesheets with multiple animation states and frames
- Create environment tilesets with custom elements and themes
- Remove background colors from images using a simple API
- Fetch available animation states and sprite styles programmatically
- Save generated assets to disk or return as base64-encoded data

## Getting Started

To use SpriteAI, you'll need to have an OpenAI API key. Once you have your API key, you can install the library using npm:

```
npm install spriteai
```

Then, you can import the relevant functions and start generating sprite assets:

```javascript
import { generateCharacterSpritesheet, generateEnvironmentSprites } from 'spriteai';

// Generate a character spritesheet
const characterSpritesheet = await generateCharacterSpritesheet('adventurer', {
  states: ['idle', 'walk', 'run', 'attack'],
  framesPerState: 6,
  size: '1024x1024',
  style: 'pixel-art',
  padding: 1,
  direction: 'right',
  save: true
});

// Generate an environment tileset
const environmentTileset = await generateEnvironmentSprites('fantasy forest', {
  elements: 4,
  size: '1024x1024',
  style: 'pixel-art',
  padding: 1,
  theme: 'fantasy',
  save: true
});
```

## API Documentation

### `generateCharacterSpritesheet(description, options)`

Generates a character spritesheet based on the provided description and options.

**Parameters:**
- `description` (string): A text description of the character to be generated.
- `options` (object, optional):
  - `states` (array of strings, optional): The animation states to include in the spritesheet. Default is `['idle', 'walk', 'run', 'attack']`.
  - `framesPerState` (number, optional): The number of frames per animation state. Default is `6`.
  - `size` (string, optional): The size of the generated spritesheet in the format `'WIDTHxHEIGHT'`. Default is `'1024x1024'`.
  - `style` (string, optional): The art style of the generated sprites. Default is `'pixel-art'`.
  - `padding` (number, optional): The amount of padding between frames in the spritesheet. Default is `1`.
  - `direction` (string, optional): The facing direction of the character. Default is `'right'`.
  - `save` (boolean, optional): If true, the generated spritesheet will be saved to disk. Default is `false`.

**Returns:**
An object with the following properties:
- `original`: The URL of the original DALL-E 3 image generation.
- `spritesheet`: The generated spritesheet as a base64-encoded data URL.
- `metadata`: An object containing details about the generated spritesheet, including the animation states, frames per state, total frames, and frame data.

### `generateEnvironmentSprites(description, options)`

Generates an environment tileset based on the provided description and options.

**Parameters:**
- `description` (string): A text description of the environment to be generated.
- `options` (object, optional):
  - `elements` (number, optional): The number of distinct environment pieces to generate. Default is `4`.
  - `size` (string, optional): The size of the generated tileset in the format `'WIDTHxHEIGHT'`. Default is `'1024x1024'`.
  - `style` (string, optional): The art style of the generated sprites. Default is `'pixel-art'`.
  - `padding` (number, optional): The amount of padding between tiles in the tileset. Default is `1`.
  - `theme` (string, optional): The theme of the environment. Default is `'fantasy'`.
  - `save` (boolean, optional): If true, the generated tileset will be saved to disk. Default is `false`.

**Returns:**
An object with the following properties:
- `original`: The URL of the original DALL-E 3 image generation.
- `tileset`: The generated tileset as a base64-encoded data URL.
- `metadata`: An object containing details about the generated tileset, including the number of elements, the theme, the dimensions, and the tile data.

### `removeBackgroundColor(inputPath, outputPath, targetColor, colorThreshold, options)`

Removes the background color from an image.

**Parameters:**
- `inputPath` (string): The file path of the input image.
- `outputPath` (string): The file path of the output image.
- `targetColor` (string): The target color to be removed, specified as a CSS color string.
- `colorThreshold` (number, optional): The color difference threshold to determine if a pixel should be made transparent. Default is `0`.
- `options` (object, optional): Additional options to be passed to the image processing library.

**Returns:**
The file path of the processed image.

### `fetchAvailableAnimationStates()`

Fetches the available animation states that can be used with the `generateCharacterSpritesheet` function.

**Returns:**
An array of strings representing the available animation states.

### `fetchAvailableSpriteStyles()`

Fetches the available sprite styles that can be used with the `generateCharacterSpritesheet` and `generateEnvironmentSprites` functions.

**Returns:**
An array of strings representing the available sprite styles.

## Examples

You can find more examples and usage guides in the [SpriteAI GitHub repository](https://github.com/your-username/spriteai).

## Reporting Issues

If you encounter any issues or have suggestions for improvements, please feel free to [open an issue on the GitHub repository](https://github.com/your-username/spriteai/issues/new).

## License

SpriteAI is released under the [MIT License](https://github.com/your-username/spriteai/blob/main/LICENSE).
