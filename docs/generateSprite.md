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
import { generateCharacterSpritesheet } from './path/to/sprite/module';

const result = await generateCharacterSpritesheet(description, options);
```

## Parameters
- `description` (string, required): A text description of the character to generate.
- `options` (object, optional):
  - `states` (string[]): Animation states to include in the spritesheet (default: `['idle', 'walk', 'run', 'attack']`).
  - `framesPerState` (number): Number of frames per animation state (default: `6`).
  - `size` (string): Size of the generated image (default: `"1024x1024"`).
  - `style` (string): Art style of the generated sprite (default: `"pixel-art"`).
  - `padding` (number): Padding between frames in the spritesheet (default: `1`).
  - `direction` (string): Character facing direction (default: `"right"`).
  - `save` (boolean): Whether to save the generated image to disk.

## Return Value
Returns an object containing:
- `original`: URL of the original generated image.
- `spritesheet`: Base64-encoded image data URL of the generated sprite sheet.
- `metadata`: Object with information about the generated spritesheet, including:
  - `states`: List of animation states.
  - `framesPerState`: Number of frames per animation state.
  - `totalFrames`: Total number of frames in the spritesheet.
  - `dimensions`: Width and height of the generated image.
  - `frameData`: Object with detailed information about each animation state.

## Examples

1. Generate a single sprite sheet:
```javascript
const result = await generateCharacterSpritesheet("A pixelated robot");
console.log(result.spritesheet);
console.log(result.metadata);
```

2. Generate multiple variations:
```javascript
const variations = await generateCharacterSpritesheet("A cartoon cat", { iterations: 3 });
variations.forEach((variation, index) => {
  console.log(`Variation ${index + 1}:`, variation.spritesheet);
});
```

## Additional SDK Functions

### fetchAvailableAnimationStates
```javascript
import { fetchAvailableAnimationStates } from './path/to/sprite/module';

const availableStates = await fetchAvailableAnimationStates();
console.log(availableStates); // ['idle', 'walk', 'run', 'attack', 'jump', 'fall', 'hurt', 'die']
```

### fetchAvailableSpriteStyles
```javascript
import { fetchAvailableSpriteStyles } from './path/to/sprite/module';

const availableStyles = await fetchAvailableSpriteStyles();
console.log(availableStyles); // ['pixel-art', 'vector', '3d', 'hand-drawn', 'anime']
```

## Notes or Considerations
- The `generateCharacterSpritesheet` function uses AI models (DALL-E 3 and GPT) to generate and analyze images, which may result in varying outputs for the same input.
- Generated sprites are optimized for walking animations and follow a specific layout (defined by the `states` and `framesPerState` options).
- The function converts images to grayscale, which may affect the final output.
- When saving images, they are stored in an 'assets' folder with a filename based on the description.
- The function may take some time to complete due to API calls and image processing.
