---
name: understand-outputs
description: >-
  Climbs an output ladder so results are easier to oversee: ASD-STE100 writing
  (or 80% of the way to it), then a diagram, then an interactive HTML page,
  then a bespoke 3Blue1Brown-style explainer video. Use when the user asks to
  understand, explain, summarize, compare, or review model output, a system, a
  decision, or a topic — and by default on explanatory replies. Implementation
  work still ships the code the user asked for.
---

# Understand outputs

We'll be spending a lot more time trying to understand the outputs of language models. A few thoughts, tips & tricks:  Writing. Something I've had success with: Ask your LLM to explain something in ASD-STE100, it's a controlled language specification originally developed for aerospace maintenance documentation. LLMs well-versed in this language and it comes with heavy constraints on clean writing style that I often find a lot more readable. Sometimes I've tried to soften it a bit e.g. ask for "80% of the way to ASD-STE100" because the spec is quite stringent. But even better:  Diagrams / images. Instead of writing, ask your LLM to create a diagram. These can be a lot easier to process, parse, and understand. But even better:  Web pages. Ask for output "in HTML" to get a beautiful, interactive webpage. LLMs are getting really good at frontend and can create beautiful experiences, animations, etc. But even better:  Explainer videos. The output format I am most bullish on is fully custom / bespoke explainer videos generated on any arbitrary topic. Experiment with things like "Create a 3b1b style video explainer on X. Use my ElevenLabs API key for audio narration". (you'd need an API key for the latter or you can ask your LLM to find you decent free alternatives that use your local compute). This is actually starting to work!  In summary: - As LLMs get better, they will do more and more of the legwork autonomously, and a lot more of our work will rise up the abstractions into oversight and understanding. - Luckily, LLMs can help here too because as intelligence and code are increasingly abundant, you can ask for large, custom, discardable software artifacts (e.g. web apps, video explainers) that would have never made sense to create before. Push the boundaries here and you'll be surprised.

## Procedure

Read [references/ste.md](references/ste.md) before you write ASD-STE100 prose.

The artifact is the answer. The chat holds a short lede at 80% of the way to ASD-STE100, plus the path to the artifact. Do not paste the page, the diagram source, or the video script into the chat.

### When this applies

Use the ladder when the user wants to understand, explain, teach, summarize, compare, or oversee a result.

When the user asks for code, a commit, or a pull request, do that work. Use the ladder for the explanation only when understanding the result is part of the job.

### Pick one rung

When two rungs can carry the idea, pick the higher one.

1. **Writing** — The answer is a few facts. Write the whole answer at 80% of the way to ASD-STE100. Use full ASD-STE100 when the user asks for the spec, or for a procedure in that language.
2. **Diagram** — The idea is a structure, a flow, a comparison, or an anatomy. Make a figure (SVG or a generated image). Use Mermaid only when a figure file is not worth opening.
3. **Web page** — The idea has parts the user will explore, compare, filter, or operate. Write one self-contained HTML file. Open it. Design it for the subject. Motion only where motion teaches the idea.
4. **Explainer video** — The idea becomes clear only as it changes through time. Make a 3Blue1Brown-style video: one idea on screen, a continuous transformation, narration locked to the change. Render with Manim on the local machine. Narration uses ElevenLabs when `ELEVENLABS_API_KEY` is already in the environment. Otherwise use local speech (`say` on macOS, or another TTS already installed). Do not ask the user to paste an API key. If the render cannot finish, deliver the web page as the storyboard and say, in one sentence, that the video file is not ready.

### Lede

One to three sentences. State the result. Give the path to the artifact when there is one. Do not recite this ladder.

### Discardable

Put the artifact where the user can open it. Do not commit it into a product repo unless the user asks.

### Honesty

You do not hold the full ASD-STE100 dictionary (about 1100 words). Apply [references/ste.md](references/ste.md). Do not claim a word is officially approved unless that file lists it.
