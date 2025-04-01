# SpriteAI SDK Documentation

## Overview

The SpriteAI SDK is a JavaScript library that leverages OpenAI's DALL-E model to generate character spritesheets and environment tilesets for game development. This updated documentation reflects the latest changes and features added to the SpriteAI SDK.

## Key Features

- Generate character spritesheets with customizable animation states, frames, and styles
- Create environment tilesets with a variety of themed elements
- Fetch available animation states and sprite styles
- Automatically remove background colors from generated images

## API Reference

### `generateCharacterSpritesheet(description, options)`

Generates a character spritesheet based on the provided description and options.

```javascript
const result = await generateCharacterSpritesheet('Warrior', {
  states: ['idle', 'walk', 'run', 'attack'],
  framesPerState: 6,
  size: '1024x1024',
  style: 'pixel-art',
  padding: 1,
  direction: 'right'
});
```

### `fetchAvailableAnimationStates()`

Fetches the available animation states that can be used with the `generateCharacterSpritesheet` function.

```javascript
const availableStates = await fetchAvailableAnimationStates();
console.log(availableStates); // ['idle', 'walk', 'run', 'attack', 'jump', 'fall', 'hurt', 'die']
```

### `fetchAvailableSpriteStyles()`

Fetches the available sprite styles that can be used with the `generateCharacterSpritesheet` and `generateEnvironmentSprites` functions.

```javascript
const availableStyles = await fetchAvailableSpriteStyles();
console.log(availableStyles); // ['pixel-art', 'vector', '3d', 'hand-drawn', 'anime']
```

### `generateEnvironmentSprites(description, options)`

Generates an environment tileset based on the provided description and options.

```javascript
const result = await generateEnvironmentSprites('Fantasy Forest', {
  elements: 4,
  size: '1024x1024',
  style: 'pixel-art',
  padding: 1,
  theme: 'fantasy'
});
```

### `removeBackgroundColor(inputPath, outputPath, targetColor, colorThreshold, options)`

Removes the specified background color from an image.

```javascript
await removeBackgroundColor('input.png', 'output.png', '#FFFFFF', 5);
```

## Installation and Usage

To use the SpriteAI SDK, install the package and import the necessary functions:

```bash
npm install spriteai
```

```javascript
import { generateCharacterSpritesheet, fetchAvailableAnimationStates, fetchAvailableSpriteStyles, generateEnvironmentSprites, removeBackgroundColor } from 'spriteai';
```

Refer to the API reference above for examples on how to use each function.

## Versioning and Updates

The SpriteAI SDK is regularly updated to incorporate new features and improvements. To ensure you are using the latest version, please check the project's repository for updates.

## Feedback and Support

If you have any questions, bug reports, or feature requests, please feel free to open an issue on the project's GitHub repository. We appreciate your feedback and will do our best to address your concerns.
