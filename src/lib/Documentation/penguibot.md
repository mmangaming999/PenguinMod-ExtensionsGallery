
# Penguibot V5.1

Penguibot is an AI-powered extension for PenguinMod, created by mmangaming999.

It adds 32 blue blocks for AI conversations, image generation, custom personalities, and persistent memory.

Penguibot uses the OpenAI API. Users must provide their own API access.

## Getting Started

1. Add the Penguibot extension to your PenguinMod project.
2. Obtain an API key from https://platform.openai.com/api-keys
3. Configure your key privately.
4. Select a chat model.
5. Start asking questions!

**Important:** Never save your secret API key as text inside a shared project. Browser-based API usage can expose keys. OpenAI API usage may also incur charges.

## Setup

- **set API key to ()** — Configures the API key for the current session.
- **test API connection** — Checks whether the API key can access OpenAI.
- **choose model []** — Selects a chat model.
- **set custom model ID to ()** — Allows a custom chat model ID when the Custom option is selected.

## Chats

Penguibot can answer questions and generate text.

```scratch
ask model [Hello! What is PenguinMod?] and wait
say (AI answer)
```

The `ask model ()` reporter returns the response directly.

The `AI answer` reporter returns the latest successful AI response.

### Advanced Chat Settings

Use `set maximum answer length to ()` to configure the response token limit.

## Mood

Mood controls the AI's personality and instructions.

For example:

```scratch
set mood to [You are a friendly pirate. Speak like a pirate.]
ask model [Introduce yourself!] and wait
say (AI answer)
```

Other blocks:

- **mood** — Returns the current personality instructions.
- **reset mood** — Restores the default personality.

The default mood is "You are an expert in PenguinMod."

## Memory

Penguibot supports three memory modes:

- **automatic** — Remembers questions and answers.
- **manual** — Uses only information explicitly added to memory.
- **off** — Does not send stored memory with new requests.

Example:

```scratch
set memory [manual v]
add [My favorite animal is a penguin.] to memory
ask model [What is my favorite animal?] and wait
say (AI answer)
```

### Advanced Memory Settings

- **memory** — Returns the stored conversation data.
- **clear memory** — Clears the active memory.
- **save memory** — Saves a memory snapshot.
- **load memory** — Restores a saved snapshot.

Saved memory snapshots can persist in the PenguinMod project file.

Note that saved conversations may contain private information. Be careful when sharing projects.

## Images

Penguibot can generate images and import them into PenguinMod as costumes or backdrops.

Example:

```scratch
generate image [A cartoon penguin on the moon] as [costume v]
```

Image settings:

- **choose image model []** — Selects an image generation model.
- **image model** — Reports the selected model.
- **set image size []** — Chooses a supported image size.
- **set image quality []** — Sets the requested image quality.

Image generation requires access to a supported OpenAI image model.

## Custom Image Sizes

Penguibot supports custom output dimensions.

Example:

```scratch
set custom image size to [40x40]
generate image [A pixel art penguin] as [costume v]
```

You can also use dimensions such as `480x360`.

Penguibot requests an API-supported image size, then resizes the generated result to the requested dimensions.

### Advanced Image Settings

- **set custom image size to ()** — Overrides the preset output dimensions.
- **clear custom image size** — Returns to preset dimensions.
- **image size** — Reports the selected output dimensions.
- **custom image size active?** — Reports whether custom dimensions are enabled.
- **resize next generated image to ()** — Sets output dimensions for future generated images.
- **clear output resize** — Removes that override.
- **resize mode []** — Chooses fit, stretch, or crop.

Resize modes:

- **fit** — Preserves aspect ratio, potentially leaving empty space.
- **stretch** — Fills the dimensions, potentially distorting the image.
- **crop** — Fills the dimensions while cropping excess content.

Valid dimensions are positive integers up to 4096 pixels per side, subject to the total pixel limit.

## Status and Errors

Penguibot includes useful status blocks:

- **AI is generating?** — True while an API request is active.
- **AI request successful?** — True after a successful request.
- **last error** — Returns the latest error message.

If something fails, check `last error`.

Common issues include an invalid API key, unavailable models, insufficient API credits, or browser networking restrictions.

## Important Information

Penguibot communicates with OpenAI directly from the browser.

- Do not publish API keys.
- Do not save secret keys in shared scripts.
- Do not assume API requests are free.
- Avoid sending personal or sensitive information without permission.
- Only load unsandboxed extensions from sources you trust.

Penguibot is an independently developed extension. It is not affiliated with or endorsed by OpenAI or PenguinMod.

## Links

Official website:
https://mmangaming999.github.io/Penguibot/

Source code:
https://github.com/mmangaming999/Penguibot

Created by mmangaming999.
