# rank-cat-charm

Ranks cat pictures by the expressiveness and charm they capture — surfacing images that convey genuine personality, emotion, and magnetic presence over those that are technically competent but emotionally unremarkable.

## Input

The function accepts an array of cat images (minimum 2). Each image is a photograph or picture depicting a cat.

```
[image_1, image_2, image_3, ...]
```

## Output

A probability distribution (array of numbers summing to approximately 1) with one score per input image. Higher scores indicate greater overall charm. The scores reflect the relative ranking of images against one another — they are comparative, not absolute.

```
[0.45, 0.05, 0.30, 0.20]
```

In the example above, the first image ranks highest for charm, followed by the third, fourth, and second.

## What It Evaluates

The function breaks charm down into three core qualities, each evaluated by a dedicated task:

### Emotional Resonance

Does the image provoke a genuine, involuntary feeling in the viewer? Warmth, humor, tenderness, delight, quiet melancholy — the specific emotion matters less than its authenticity. A blurry snapshot capturing a moment of undeniable feeling outranks a perfectly lit portrait that stirs nothing. This quality measures the bridge between the image and the viewer's heart.

### Narrative Character

Does the image reveal who this cat is as an individual? The best cat pictures feel like a single frame pulled from a larger life — you sense the before and after, and you understand the cat's personality. Curiosity in the tilt of a head, mischief beside a knocked-over glass, dignity in a regal posture. Images where the cat could be any cat in any moment score low; images that feel like character studies score high.

### Magnetic Presence

Does the image have raw stopping power — the ability to make someone pause, look longer, and want to share it? This is the instinctive "it factor" that separates images you scroll past from images that reach out and grab you. Whether through dramatic intensity, comedic timing, or unexpected tenderness, the image must demand a reaction rather than passively wait to be noticed.

## Use Cases

- **Social media curation**: Surface the most engaging cat content so pictures with genuine spark rise above the noise.
- **Photo contests**: Assist judges in identifying entries that go beyond technical execution and actually move people.
- **Personal photo libraries**: Sort a collection so the most expressive and memorable moments with a beloved pet are easy to find.
- **Editorial and creative work**: Choose hero images, greeting card photos, or gallery selections by finding the pictures with the most life in them.
- **Content moderation and recommendation**: Prioritize high-charm content in feeds, recommendations, or featured sections.

## How It Works

The function uses three vector completion tasks, each framing the ranking as a natural conversational choice rather than a direct evaluation. The input images become candidate responses that an LLM selects between, and the model's preferences across all three tasks are combined into a final ranking.

1. **Emotional curation task**: Frames the choice as selecting the next picture for a collection called "Pictures That Make You Feel Something."
2. **Character portrait task**: Frames the choice as selecting a picture for a photo book called "Cat Characters" — portraits revealing individual personality.
3. **Stopping power task**: Frames the choice as picking the single best cat picture to post online — the one with the most raw ability to make someone stop scrolling.

The weighted combination of scores across these three tasks produces the final charm ranking.

## Key Principles

- **Feeling over technique**: Technical quality (lighting, resolution, composition) is not what this function measures. A technically imperfect image that captures something real will always outrank a polished image that captures nothing.
- **Individuality over anonymity**: Pictures that reveal a specific cat's character rank above generic, interchangeable cat photos.
- **Active over passive**: Images that demand attention and provoke a reaction rank above images that are merely pleasant.
- **Comparative ranking**: Scores are relative to the other images in the input set, not absolute measures of charm.
