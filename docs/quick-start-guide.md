# Quick Start Guide

This guide will help you get started with using the `generateSprite` function to create AI-generated sprite sheets for your projects.

## Installation

To begin, make sure you have the sprite module installed in your project. You can typically do this by importing it from the appropriate path:

```javascript
import { sprite } from './path/to/sprite/module';
```

## Basic Usage

Here's a simple example to generate a single sprite sheet:

```javascript
const description = "A pixelated robot";
const result = await sprite.generateSprite(description);

console.log(result.messages); // Log frame dimensions
console.log(result.image); // Log base64-encoded image data URL
```

This will generate a sprite sheet of a pixelated robot with default settings.

## Customizing Your Sprite

You can customize your sprite generation by passing options:

```javascript
const description = "A cartoon cat";
const options = {
  iterations: 3,
  size: "2048x2048",
  save: true
};

const variations = await sprite.generateSprite(description, options);

variations.forEach((variation, index) => {
  console.log(`Variation ${index + 1}:`, variation.messages);
});
```

This example generates three variations of a cartoon cat sprite, with a larger image size, and saves the results to disk.

## Understanding the Output

The `generateSprite` function returns an object (or array of objects for multiple iterations) containing:

- `messages`: A JSON object with `frameHeight` and `frameWidth` information.
- `image`: A base64-encoded image data URL of the generated sprite sheet.

## Tips for Best Results

1. Be specific in your descriptions for more accurate results.
2. Experiment with different iterations to get varied options.
3. The default sprite sheet layout is optimized for walking animations (6 frames in a 2x3 grid).
4. Generated images are converted to grayscale, which may affect the final output.
5. When saving is enabled, images are stored in an 'assets' folder with a filename based on the description.

## Next Steps

- Explore more advanced options and configurations.
- Integrate the generated sprites into your game or application.
- Experiment with different descriptions to see how they affect the output.

Remember that the AI models used (DALL-E 3 and GPT) may produce varying results for the same input, so don't be afraid to generate multiple options if you're not satisfied with the initial output.