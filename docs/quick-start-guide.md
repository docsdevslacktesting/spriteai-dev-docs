# Quick Start Guide

## Introduction

SpriteAI is a powerful tool for generating sprite sheets and landscape sprites using AI. This guide will help you get started with the main functions: `generateCharacterSpritesheet` and `generateLandscapeSprite`.

## Installation

First, ensure you have Node.js installed on your system. Then, install the required dependencies:

```bash
npm install openai axios sharp jimp fs path
```

## Usage

### Generating a Character Spritesheet

To generate a character spritesheet, use the `generateCharacterSpritesheet` function:

```javascript
import { generateCharacterSpritesheet } from './path/to/spriteai';

const description = 'A pixelated warrior with sword and shield';
const options = {
  states: ['idle', 'walk', 'run', 'attack'],
  framesPerState: 6,
  size: '1024x1024',
  style: 'pixel-art',
  direction: 'right',
  save: true
};

const result = await generateCharacterSpritesheet(description, options);
console.log(result);
```

#### Options

- `states`: Array of animation states (default: ['idle', 'walk', 'run', 'attack'])
- `framesPerState`: Number of frames per animation state (default: 6)
- `size`: Output size of the spritesheet (default: '1024x1024')
- `style`: Art style (default: 'pixel-art')
- `direction`: Base direction of the character (default: 'right')
- `save`: Whether to save the generated image (default: false)

### Generating a Landscape Sprite

To generate a landscape sprite, use the `generateLandscapeSprite` function:

```javascript
import { generateLandscapeSprite } from './path/to/spriteai';

const description = 'A lush forest with a winding river';
const options = {
  size: '1024x1024',
  style: 'pixel-art',
  timeOfDay: 'day',
  weather: 'clear',
  perspective: 'side-scrolling',
  save: true
};

const result = await generateLandscapeSprite(description, options);
console.log(result);
```

#### Options

- `size`: Output size of the landscape sprite (default: '1024x1024')
- `style`: Art style (default: 'pixel-art')
- `timeOfDay`: Time of day setting (default: 'day')
- `weather`: Weather conditions (default: 'clear')
- `perspective`: Perspective of the landscape (default: 'side-scrolling')
- `save`: Whether to save the generated image (default: false)

## Return Value

Both functions return an object containing:

- `original`: URL of the original generated image
- `spritesheet` or `landscape`: Base64-encoded image data of the processed sprite
- `metadata`: Object containing information about the generated sprite

## Saving Generated Images

If the `save` option is set to `true`, the generated images will be saved in an 'assets' folder in your current working directory.

## Notes

- The functions use OpenAI's DALL-E 3 model for image generation, which may result in varying outputs for the same input.
- Generated sprites are optimized for game development and follow specific layouts based on the function used.
- The image generation process may take some time due to API calls and image processing.

For more advanced usage and additional functions, refer to the full documentation.