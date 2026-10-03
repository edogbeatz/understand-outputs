# ASD-STE100 rules in force

ASD-STE100 (Simplified Technical English) is a controlled language for aircraft maintenance documentation. Specification ASD-STE100. Owner: ASD. Maintained by the ASD Simplified Technical English Maintenance Group (STEMG). Issue history on the work card: 1979 AECMA, 1986 Simplified English, 2005 ASD-STE100, current issue maintained by ASD.

The official dictionary is about 1100 approved words. Each approved word has one part of speech and one meaning. This file is a working subset from the specification sheet, not the dictionary.

## 80% and full spec

Default is **80% of the way to ASD-STE100**.

Keep these even at 80%:

- One idea in each sentence. One topic in each paragraph.
- The same word for the same thing, every time.
- Active voice in procedures.
- A command is the imperative.
- Do not leave out "the", "a", or "this".
- No noun stack longer than three words.
- A vertical list when the text is complex.
- Short sentences. Say the limit below, then stop.

Softening that makes it 80%:

- Everyday words are allowed when the approved word would hide the meaning. Code identifiers, product names, and the user's words stay as they are.
- You may go a little past the word cap when a proper name forces it.
- You may use one progressive verb when the action is ongoing and the simple present would be false.
- Connective tissue ("that", "and") may stay.

Full ASD-STE100 when the user asks for the spec or for a maintenance-style procedure. Then the verb-form bans and the word caps are hard. Still do not invent dictionary status for words this file does not list.

## Sentence caps

| Kind | Max words | Verb |
| --- | --- | --- |
| Procedural sentence | 20 | Imperative, or the approved command pattern |
| Descriptive sentence | 25 | Simple present |
| Descriptive paragraph | 6 sentences | One topic |
| Noun cluster | 3 words | |
| Instructions in one sentence | 1 | Two are allowed only when the actions are simultaneous |

## Approved verb forms

- Command (imperative): "Close the valve."
- Simple present: "The valve closes."
- Simple past: "The valve closed."
- Simple future: "The valve will close."
- Infinitive: "Turn the knob to close it."

Not approved as the main verb:

- Progressive: "The valve is closing."
- Perfect: "The valve has closed."
- Passive in a procedure: "The valve must be closed."

## Sample dictionary

Approved keywords are in uppercase. Unapproved words are in lowercase. The approved example is normal prose, not keywords.

| Word | Status | Use this | Approved example | Not approved |
| --- | --- | --- | --- | --- |
| CLOSE (v) | Approved | To move together to stop flow | Close the valve. | |
| close (adj) | Not approved | NEAR | | |
| commence (v) | Not approved | START | START the pump. | Commence pumping. |
| ensure (v) | Not approved | MAKE SURE | MAKE SURE that the switch is off. | Ensure the switch is off. |
| prior to (prep) | Not approved | BEFORE | BEFORE you start the engine. | Prior to starting the engine. |
| replenish (v) | Not approved | FILL | FILL the reservoir. | Replenish the reservoir. |
| utilize (v) | Not approved | USE | USE a torque wrench. | Utilize a torque wrench. |
| approximately (adv) | Not approved | ABOUT | Wait ABOUT 10 minutes. | Wait approximately 10 minutes. |
| in order to | Not approved | TO | Remove the panel TO get access. | Remove the panel in order to get access. |
| TEST (v) | Approved | To find if it operates correctly | TEST the circuit. | |

## Sentence pattern

Unapproved:

"It is imperative that the operator ensures the hydraulic reservoir is replenished prior to commencing operation."

Approved:

"Make sure that the hydraulic reservoir is full before you start the operation."

Marks on the approved sentence: command form, technical name ("hydraulic reservoir"), active voice, not "replenished", not "prior to", not "commencing". About 13 words. Procedural limit 20.

## Safety

- WARNING: risk of injury.
- CAUTION: risk of damage.
- Write a clear command. Then state the risk.

Approved:

"WARNING: Do not touch the brake unit until it is cool. Hot parts can cause injury."

## Practices

- Use the same word for the same thing every time.
- Do not leave out words like "the", "a", and "this".
- Use the active voice in procedures.
- Use a vertical list for complex text.
- Write one topic in each paragraph.

## Video render

Make the video on [ngram](https://www.ngram.com/). Docs: [MCP](https://www.ngram.com/docs/mcp), [API](https://www.ngram.com/docs/getting-started).

1. Write the brief: audience, length, tone, and the prompt. Show it. Stop.
2. Wait for a yes that names this brief. Do not start a render, and do not spend credits, before that yes.
3. If ngram MCP is connected, read the tool schema. Use `prepare_video`, then `create_video` after the yes. If those tools are absent, use `create_video_from_text` after the yes.
4. Do not ask for an API key in chat. If ngram is not connected, say so in one sentence. Give the storyboard as a web page.
5. Use Manim on the local machine only when the user asks for a local file. One idea transforms into the next. Speech uses ElevenLabs only when `ELEVENLABS_API_KEY` is already set. Otherwise use local speech.
