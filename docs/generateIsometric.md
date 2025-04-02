# Generating Isometric Sprites

## Introduction

The `generateIsometric()` function is a powerful tool that allows you to generate isometric sprite animations from a set of provided sprite images. This can be particularly useful for creating 2.5D or isometric game environments, where characters and objects need to be depicted from an angled perspective.

## Usage

To use the `generateIsometric()` function, you'll need to provide an array of sprite images that represent the different frames of an animation. The function will then composite these images into an isometric projection, creating a new set of sprite frames that can be used in your game or application.

Here's an example of how to use the function:

```javascript
import { generateIsometric } from 'spriteai';

const spriteImages = [
  'sprite1.png',
  'sprite2.png',
  'sprite3.png',
  'sprite4.png',
];

const isometricSprites = generateIsometric(spriteImages, {
  tileSize: 64,
  angle: 30,
  perspective: 0.5,
});
```

In this example, the `generateIsometric()` function takes an array of sprite image paths and generates a new array of isometric sprite images. You can customize the output by adjusting the `tileSize`, `angle`, and `perspective` parameters.

## Configuration Options

The `generateIsometric()` function accepts the following configuration options:

- `tileSize` (number): The size of each sprite tile in pixels.
- `angle` (number): The angle of the isometric projection in degrees (typically between 30-45 degrees).
- `perspective` (number): The amount of perspective to apply to the isometric projection (between 0-1).
- `backgroundColor` (string): The background color to use for the isometric sprites (default is transparent).
- `padding` (number): The amount of padding to add around each isometric sprite (default is 0).

You can experiment with these settings to achieve the desired look and feel for your isometric sprites.

## Example Project

For a complete example of how to use the `generateIsometric()` function, check out the [Isometric Sprite Generator project](https://github.com/docsdevslacktesting/spriteai-dev-docs/tree/main/examples/isometric-sprite-generator) in the SpriteAI documentation repository.
