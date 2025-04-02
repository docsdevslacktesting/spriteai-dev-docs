# Generate a Sprite

Hey there, fellow sprite enthusiast! 👋 Ready to bring some pixelated magic to life? Let's dive into how you can whip up a cool sprite using our nifty `generateSprite` function.

## The Basics

First things first, here's what you need to know about `generateSprite`:

```typescript
function generateSprite(prompt: string, style?: string): Promise
```

This bad boy takes your creative ideas and turns them into awesome sprites. Cool, right?

## How to Use It

It's super easy to use. Here's the lowdown:

1. **prompt** (required): This is where you let your imagination run wild! Describe what you want your sprite to look like. Go nuts!

2. **style** (optional): Feeling fancy? You can specify a style for your sprite. If you're not picky, no worries - we'll hook you up with our default style.

## What You Get Back

After you call `generateSprite`, it'll return a `Promise` that resolves to a `Uint8Array`. This array is packed with all the pixel data for your brand new sprite. It's like getting a gift, but instead of unwrapping paper, you're unwrapping bytes!

## Example Time!

Let's see this function in action:

```typescript
import { generateSprite } from 'sprite-generator';

async function createAwesomeSprite() {
  try {
    const spriteData = await generateSprite('A cool robot with laser eyes', 'pixelart');
    console.log('Woohoo! Sprite created successfully!');
    // Do something awesome with your new sprite data
  } catch (error) {
    console.error('Oops! Something went wrong:', error);
  }
}

createAwesomeSprite();
```

In this example, we're creating a rad robot with laser eyes in a pixelart style. How cool is that?

## Pro Tips

- Be as specific as you can in your prompt. The more details, the better!
- Experiment with different styles to find your favorite look.
- If you're stuck, try describing a character from your favorite game or movie.

So there you have it! Now go forth and create some amazing sprites. The pixel world is your oyster! 🎮✨

Happy sprite-ing!