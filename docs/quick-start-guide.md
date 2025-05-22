# Quick Start Guide

This guide will help you get started with using the SpriteAI library to generate character spritesheets and landscape sprites using AI-powered image generation.

## Installation

First, install the SpriteAI library and its dependencies:

```bash
npm install spriteai openai axios sharp jimp
```

## Setting up OpenAI API

Before using SpriteAI, make sure you have an OpenAI API key. Set it as an environment variable:

```bash
export OPENAI_API_KEY=your_api_key_here
```

## Generating a Character Spritesheet

To generate a character spritesheet, use the `generateCharacterSpritesheet` function:

```javascript
import { generateCharacterSpritesheet } from 'spriteai';

async function generateCharacter() {
  const result = await generateCharacterSpritesheet('A pixelated warrior', {
    states: ['idle', 'walk', 'run', 'attack'],
    framesPerState: 6,
    size: '1024x1024',
    style: 'pixel-art',
    save: true
  });

  console.log('Spritesheet URL:', result.spritesheet);
  console.log('Metadata:', result.metadata);
}

generateCharacter();
```

This will generate a spritesheet with four animation states (idle, walk, run, attack), each with 6 frames.

## Generating a Landscape Sprite

To generate a landscape sprite, use the `generateLandscapeSprite` function:

```javascript
import { generateLandscapeSprite } from 'spriteai';

async function generateLandscape() {
  const result = await generateLandscapeSprite('A lush forest with a river', {
    size: '1024x1024',
    style: 'pixel-art',
    timeOfDay: 'sunset',
    weather: 'clear',
    perspective: 'side-scrolling',
    save: true
  });

  console.log('Landscape URL:', result.landscape);
  console.log('Metadata:', result.metadata);
}

generateLandscape();
```

This will generate a pixel art landscape sprite of a forest with a river at sunset.

## Customizing Output

Both functions accept various options to customize the output:

- `size`: Dimensions of the output image (e.g., '1024x1024')
- `style`: Art style (e.g., 'pixel-art')
- `save`: Whether to save the generated image to disk

For character spritesheets:
- `states`: Array of animation states
- `framesPerState`: Number of frames per animation state
- `direction`: Base direction of the character

For landscapes:
- `timeOfDay`: Time setting (e.g., 'day', 'night', 'sunset')
- `weather`: Weather conditions (e.g., 'clear', 'rainy', 'foggy')
- `perspective`: Perspective of the landscape (e.g., 'side-scrolling', 'top-down')

## Working with Results

Both functions return an object containing:

- A base64-encoded image data URL (`spritesheet` or `landscape`)
- The original image URL from DALL-E
- Metadata about the generated image

You can use these results to display the images in your application or save them for later use.

## Notes

- The library uses OpenAI's DALL-E 3 model for image generation, which may take some time to process.
- Generated images are saved in an 'assets' folder in your current working directory if the `save` option is set to `true`.
- The quality and consistency of generated sprites may vary due to the nature of AI-generated content.

For more detailed information on each function and its options, refer to the full documentation.