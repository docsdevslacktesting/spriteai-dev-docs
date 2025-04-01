---
slug: /
sidebar_position: 1
---

# generateSprite Documentation

## Brief Description
`generateSprite` is a function that generates a sprite sheet image based on a given description, using AI-powered image generation and analysis.

## Usage
To use `generateSprite`, import it from the sprite module and call it with a description of the character you want to generate.

```javascript
import { generateCharacterSpritesheet } from './spriteAI';

const result = await generateCharacterSpritesheet(description, options);
```

## Parameters
- `description` (string, required): A text description of the character to generate.
- `options` (object, optional):
  - `states` (array): Animation states to include (default: `['idle', 'walk', 'run', 'attack']`).
  - `framesPerState` (number): Number of frames per animation state (default: `6`).
  - `size` (string): Size of the generated image (default: `'1024x1024'`).
  - `style` (string): Art style for the generated sprites (default: `'pixel-art'`).
  - `padding` (number): Spacing between frames in the spritesheet (default: `1`).
  - `direction` (string): Character facing direction (default: `'right'`).
  - `save` (boolean): Whether to save the generated image to disk (default: `false`).

## Return Value
Returns an object containing:
- `original`: URL of the original generated image.
- `spritesheet`: Base64-encoded image data URL of the generated sprite sheet.
- `metadata`: Information about the generated spritesheet, including:
  - `states`: The animation states included.
  - `framesPerState`: Number of frames per animation state.
  - `totalFrames`: Total number of frames in the spritesheet.
  - `dimensions`: Width and height of the generated image.
  - `frameData`: Detailed information about each animation state.

## Examples

1. Generate a single sprite sheet:
```javascript
const result = await generateCharacterSpritesheet("A pixelated robot");
console.log(result.spritesheet);
console.log(result.metadata);
```

2. Generate multiple variations:
```javascript
const result = await generateCharacterSpritesheet("A cartoon cat", { iterations: 3 });
result.forEach((variation, index) => {
  console.log(`Variation ${index + 1}:`, variation.metadata);
});
```

## Notes or Considerations
- The function uses AI models (DALL-E 3 and GPT) to generate and analyze images, which may result in varying outputs for the same input.
- Generated sprites are optimized for walking animations and follow a specific layout (multiple rows with frames per row).
- The function converts images to grayscale, which may affect the final output.
- When saving images, they are stored in an 'assets' folder with a filename based on the description.
- The function may take some time to complete due to API calls and image processing.
