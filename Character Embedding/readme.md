# Training photos

## Images filename pattern
`[prompt_spaces] ([seed].[datetime])`

## Positive Prompt
> an extreme closeup front shot photo of %your character's look% (naked:1.3), %your character's body shape%, %your character's hairstyle%, (neutral gray background:1.3), neutral face expression

## Negative Prompt
> (gray hair, glasses, earrings, necklace, high heels, tattoo:1.3),

> (deformed, distorted, disfigured, mutated, mangled, disgusting, amputated:1.3), (text, frame, watermark, signature, copyright, username, error:1.4), poorly drawn, ugly, blurry,

> bad anatomy, wrong anatomy, extra limb, missing limb, floating limbs, (mutated hands and fingers:1.4), disconnected limbs,

## txt2img settings
* Sampling method: DPM++ 2M Karras
* Sampling steps: 30
* Restore Faces: On
* Tiling: Off
* Hires. fix: Off
* Width: 512
* Height: 512
* CFG Scale: 7
* Seed: -1
* Batch count: 2
* Batch size: 8

## Script
* `X/Y/Z Plot`
* X type: `Prompt S/R`
* X values:
> an extreme closeup, a medium closeup, a closeup, a medium shot, a full body
* Y type: `Prompt S/R`
* Y values:
> front shot, rear angle, side angle, shot from above, low angle shot
* Z type: `Nothing`
* Draw Legend
* Keep -1 for seeds

## Filtering
* poor quality, messed up, cropped
* clothing, jewlery, tattos, accessories, effects
* wrong hair, face, body style
* mutations or weird angles
* anything that doesn't look like the character we want

Pare down to 25 good pics. Include different angles and zooms

## Renaming
* Remove things that belong to the character: the character's look; the character's body shape; the character's hairstyle
* Keep things that are in all pics but don't belong to the character: naked, neutral gray background
* Remove angles, they don't help training
* Keep zoom levels
* Include character's name in the prompt. e.g.
> a closeup photo of myCh4r4ct3rHere naked, neutral gray background (1234567890).png

## Zoom definitions
1) Can you see the knees? If so, it's probably "a full body" photo.
2) Can you see the waist? If so, it's probably "a medium shot" photo.
3) Can you see the breast area? If so, it's probably "a closeup" photo.
4) Can you see the neck area? If so, it's probably "a medium closeup" photo.
5) If none of the above, it's probably "an extreme closeup" photo.

# Embedding creation

## Character embedding creation
* Name: Choose a unique name that wouldn't appear in any other training. Use prefixes and numbers
* Initialization text: A specific starting point for training to apply everything it has learned. Like `woman`
* Number of vectors per token: 8-10 ish
* Overwrite Old Embedding