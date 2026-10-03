---
name: understand-outputs
description: >-
  Climbs an output ladder so results are easier to oversee: ASD-STE100 writing
  (or 80% of the way to it), then a diagram, then a ChatGPT Site after the
  user approves that site's brief, then a bespoke explainer video on
  ngram.com after the user approves that video's brief. Use when the user asks to
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
3. **Web page** — The idea has parts the user will explore, compare, filter, or operate. Host it as a [ChatGPT Site](https://learn.chatgpt.com/docs/sites). Approval comes first.
   - Write the brief in the chat: who uses the site, what they can do, and the prompt. The prompt includes the word "website" or `@Sites`. Then stop.
   - Create the site only after the user says yes to that brief. A yes on an earlier site does not cover this one.
   - In ChatGPT, or in Codex in the ChatGPT desktop app, start the Site after the yes. Leave access as ChatGPT sets it: the owner and workspace admins. Share it, or publish it on the internet, only when the user asks. Sites are listed at [chatgpt.com/sites](https://chatgpt.com/sites). Help: [Creating and managing ChatGPT Sites](https://help.openai.com/en/articles/20001339).
   - If this agent cannot create a Site, give the approved prompt and write one self-contained HTML file. Say, in one sentence, that the hosted site is the ChatGPT one.
   - Example prompt: `@Sites Build a website that explains the output ladder. The reader picks a rung. Writing, diagram, page, and video each do one job. Use ASD-STE100 at 80%.`
4. **Explainer video** — The idea becomes clear only as it changes through time. Make it on [ngram](https://www.ngram.com/). Approval comes first.
   - Write the brief in the chat: audience, length, tone, and the prompt you will send. Then stop.
   - Create the video only after the user says yes to that brief. A yes on an earlier video does not cover this one.
   - When ngram MCP is connected at `https://mcp.ngram.com`, read the tool schema first. Call `prepare_video` to show the plan. Call `create_video` only after the yes. If those tools are absent, use `create_video_from_text` after the yes.
   - Do not ask the user to paste an API key. If ngram is not connected, say so in one sentence and point to [the MCP docs](https://www.ngram.com/docs/mcp). Deliver the web page as the storyboard.
   - Render locally with Manim only when the user asks for a local file. Narration then uses ElevenLabs when `ELEVENLABS_API_KEY` is already set. Otherwise use local speech.

### Lede

One to three sentences. State the result. Give the path to the artifact when there is one. Do not recite this ladder.

### Discardable

Put the artifact where the user can open it. Do not commit it into a product repo unless the user asks.

### Honesty

You do not hold the full ASD-STE100 dictionary (about 1100 words). Apply [references/ste.md](references/ste.md). Do not claim a word is officially approved unless that file lists it.
