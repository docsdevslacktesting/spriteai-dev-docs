# Generating Sprites with SpriteAI

Hey there, fellow game developer! 👋 Ready to create some awesome sprites for your game? Let's dive into how you can use SpriteAI to whip up some cool character designs.

## Getting Started

First things first, you'll need to import the `generateSprite` function from our nifty SpriteAI library. It's super easy:

```javascript
import { generateSprite } from 'spriteai';
```

## The Magic Function

Now, let's talk about the star of the show - the `generateSprite` function. Here's what it looks like:

```javascript
generateSprite(prompt, options)
```

### Parameters

- `prompt` (string): This is where you describe your sprite. Get creative! Want a "cute blue robot with rocket feet"? Just say so!
- `options` (object): Optional. This is where you can fine-tune your sprite generation. We'll get into the details in a bit.

### What You Get Back

The function returns a Promise that resolves to an object with these goodies:

- `sprite` (string): A Base64 encoded PNG of your shiny new sprite.
- `seed` (number): A seed value. Handy if you want to recreate this exact sprite later.

## Customizing Your Sprite

Alright, let's talk about those optional `options`. You can tweak these to get your sprite just right:

- `seed` (number): Got a favorite number? Use it as a seed to get consistent results.
- `style` (string): Pick a vibe for your sprite. Options are "pixel", "cartoon", or "realistic".
- `viewpoint` (string): How do you want to see your sprite? Choose "front", "side", "top", or "isometric".
- `background` (string): What's behind your sprite? Go for "transparent", "white", or "black".

## Let's Make Some Sprites!

Ready to see it in action? Check out these examples:

```javascript
// Let's make a basic sprite
generateSprite('A happy sun wearing sunglasses')
  .then(result => console.log('Here's your sunny sprite!', result.sprite))
  .catch(error => console.error('Oops, something went wrong:', error));

// Now, let's get fancy with some options
const options = {
  style: 'pixel',
  viewpoint: 'isometric',
  background: 'transparent'
};

generateSprite('A fierce dragon breathing fire', options)
  .then(result => console.log('Your dragon is ready to roar!', result.sprite))
  .catch(error => console.error('Uh-oh, dragon troubles:', error));
```

And there you have it! You're now ready to populate your game with all sorts of cool sprites. Happy generating! 🎮✨