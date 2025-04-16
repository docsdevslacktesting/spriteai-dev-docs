# Quick Start Guide

## Introduction

SpriteAI is a powerful library for generating sprite sheets and landscape sprites using AI. This guide will help you get started with the main functions: `generateCharacterSpritesheet` and `generateLandscapeSprite`.

## Installation

First, install the SpriteAI library in your project:

```bash
npm install spriteai
```

## Generating a Character Spritesheet

To generate a character spritesheet:

```javascript
import { generateCharacterSpritesheet } from 'spriteai';

const description = 'A pixelated warrior with a sword and shield';
const options = {
  states: ['idle', 'walk', 'run', 'attack'],
  framesPerState: 6,
  size: '1024x1024',
  style: 'pixel-art',
  direction: 'right',
  save: true
};

const result = await generateCharacterSpritesheet(description, options);
console.log(result.metadata);
console.log(result.spritesheet); // Base64 encoded image
```

### Options

- `states`: Animation states to generate (default: ['idle', 'walk', 'run', 'attack'])
- `framesPerState`: Number of frames per animation state (default: 6)
- `size`: Output size (default: '1024x1024')
- `style`: Art style (default: 'pixel-art')
- `direction`: Base direction of character (default: 'right')
- `save`: Whether to save the generated image (default: false)

## Generating a Landscape Sprite

To generate a landscape sprite:

```javascript
import { generateLandscapeSprite } from 'spriteai';

const description = 'A lush forest with a winding river';
const options = {
  size: '1024x1024',
  style: 'pixel-art',
  timeOfDay: 'sunset',
  weather: 'clear',
  perspective: 'side-scrolling',
  save: true
};

const result = await generateLandscapeSprite(description, options);
console.log(result.metadata);
console.log(result.landscape); // Base64 encoded image
```

### Options

- `size`: Output size (default: '1024x1024')
- `style`: Art style (default: 'pixel-art')
- `timeOfDay`: Time of day setting (default: 'day')
- `weather`: Weather conditions (default: 'clear')
- `perspective`: Perspective view (default: 'side-scrolling')
- `save`: Whether to save the generated image (default: false)

## Working with Generated Sprites

Both functions return an object containing:

- `original`: URL of the original generated image
- `spritesheet` or `landscape`: Base64 encoded image data
- `metadata`: Information about the generated sprite

You can use the Base64 encoded image data to display the sprite in your application or save it to a file.

## Saving Generated Sprites

When the `save` option is set to `true`, the generated sprites are automatically saved in the `assets` folder of your project. The filenames are based on the provided descriptions.

## Next Steps

Explore more advanced options and features in the full documentation. Happy sprite generating!