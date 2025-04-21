# Spectre Steganography System

**Spectre** is a zero-width character steganography system that embeds hidden messages into `.docx` files using ChatGPT-4o or o3. It automates the generation of cover text, message encoding, and decoding—all using prompt engineering, not code.

**Why the name "Spectre"?** ChatGPT suggested it after hearing the concept.

## What’s new (v1.1 - Optimised Ruleset)
* **One-file setup** - All core rules merged into `Spectre_Ruleset.md`. 
* **Smaller prompt** - massive token reduction, completely re-written for LLM readability.
* **Updated encoding logic** - Switched from the old 73 row lookup table to a simple algorithm for LLM parsing speed.

## How It Works
- Each character of your secret message is encoded using 'invisible' **zero-width Unicode characters**.
- These encoded sequences are embedded into the cover letter (typically after the first paragraph) to minimise visual disruption.
- Messages are only accessible with the correct **encode or decode password**.

## Why .docx files?
- ChatGPT conversation text is piped through several layers — tokeniser, markdown renderer, browser UI, etc. Any of these can strip or mangle zero‑width characters. On the other hand when asked to create a .docx ChatGPT writes zero‑width characters straight into the document XML during generation. Mainstream `.docx` viewers keep those characters intact and render them invisibly, so the payload travels safely and remains unseen to casual readers.

## How to Use
### Encoding a Message
1. Upload the Spectre_Ruleset.md instruction file into a ChatGPT-4o or -o3 conversation or **Project Space** (recommended).
2. Ask ChatGPT to write a letter. It will ask:
   - Who is the letter for?
   - What is the occasion?
   - How long should the letter be?
   - Who is the letter from?
3. To enable secret encoding, include the password:
   ```
   SpiralArchitect
   ```
4. When prompted to include anything else in the letter, type your secret message. This will be embedded invisibly.
5. You’ll receive a `.docx` file download containing both the visible letter and hidden message.

---

### Decoding a Message
1. Upload a Spectre-encoded `.docx` file to a ChatGPT-4o conversation or **Project Space** that has been Spectre-enabled.
2. Provide the decoding password:
   ```
   NationalAcrobat
   ```
3. ChatGPT will extract and display the hidden message—if one exists.

---

## Limitations

1. **Model compatibility**: Currently works best with **ChatGPT-4o**. Older GPT models and other LLMs (e.g., Claude, Gemini) often fail or ignore instructions. UPDATE: ChatGPT-o3 handles the instructions extremely well.
2. **Not encryption**: This is pure steganography. No cryptographic strength—just secrecy through invisibility, a human with basic knowledge of cyphers can decode the messages with a moderate sample size and a few hours.
3. **LLM instability**: LLMs are frequently updated. What works today might break tomorrow. Your mileage will vary. Future projects will attempt to address this.
4. **Detectability**: Anyone who knows what zero-width characters are—and how to extract them—can find the existence of the message.

## Final Note
This project is about exploring and bending the boundaries of Prompt Engineering and AI-based covert communications, not creating a foolproof realworld ready system. 
