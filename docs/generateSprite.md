{
  "updatedDocumentation": "# Generating Sprites with SpriteAI

## Overview

SpriteAI is a powerful library that enables you to generate sprites programmatically. This documentation will guide you through the process of using the `generateSprite` function to create sprites based on your application's needs.

## Prerequisites

Before using the `generateSprite` function, ensure that you have the SpriteAI library installed in your project. You can install it using npm:

```
npm install spriteai
```

## Generating a Sprite

To generate a sprite, you can use the `generateSprite` function provided by the SpriteAI library. This function takes an object as an argument, which contains the necessary parameters to configure the sprite.

Here's an example of how to use the `generateSprite` function:

```javascript
const { generateSprite } = require('spriteai');

const spriteOptions = {
  width: 64,
  height: 64,
  backgroundColor: '#ffffff',
  foregroundColor: '#000000',
  text: 'Hello, World!',
  fontSize: 24,
  fontFamily: 'Arial',
  fontWeight: 'bold',
  padding: 10
};

const spriteBuffer = await generateSprite(spriteOptions);
```

In this example, the `spriteOptions` object defines the properties of the sprite to be generated, such as its size, background and foreground colors, text, font settings, and padding.

The `generateSprite` function returns a `Buffer` object, which represents the generated sprite image. You can then use this buffer to save the sprite to a file, display it in your application, or perform any other necessary operations.

## Customizing the Sprite

The `generateSprite` function provides several options to customize the appearance of the generated sprite. You can adjust the following properties:

- `width`: The width of the sprite in pixels.
- `height`: The height of the sprite in pixels.
- `backgroundColor`: The background color of the sprite, specified as a hex value (e.g., '#ffffff' for white).
- `foregroundColor`: The foreground color of the sprite, specified as a hex value (e.g., '#000000' for black).
- `text`: The text to be displayed on the sprite.
- `fontSize`: The size of the text, in pixels.
- `fontFamily`: The font family to be used for the text.
- `fontWeight`: The weight of the font, such as 'normal', 'bold', or 'italic'.
- `padding`: The amount of padding, in pixels, around the text within the sprite.

Feel free to experiment with these options to create the desired sprite appearance for your application.

## Conclusion

The `generateSprite` function in the SpriteAI library provides a simple and flexible way to generate sprites programmatically. By customizing the various options, you can create sprites that perfectly fit your application's needs. If you have any further questions or need assistance, please don't hesitate to reach out to the SpriteAI team.
}