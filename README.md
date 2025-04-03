# Spectre Steganography System

**Spectre** is a zero-width character steganography system that embeds hidden messages into `.docx` files using ChatGPT-4o. It automates the generation of cover text, message encoding, and decoding—all using prompt engineering, not code.

**Why the name "Spectre"?** ChatGPT suggested it after hearing the concept.

## How It Works
- Each character of your secret message is encoded using 'invisible' **zero-width Unicode characters**.
- These encoded sequences are embedded into the cover letter (typically after the first paragraph) to minimise visual disruption.
- Messages are only accessible with the correct **encode or decode password**.

## How to Use
### Encoding a Message
1. Upload the four `.txt` instruction files into a ChatGPT-4o conversation or a **Project Space** (recommended).
2. Ask the assistant to write a letter. It will ask:
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
1. Upload a Spectre-encoded `.docx` file.
2. Provide the decoding password:
   ```
   NationalAcrobat
   ```
3. ChatGPT-4o will extract and display the hidden message—if one exists.

---

## Limitations

1. **Model compatibility**: Currently works best with **ChatGPT-4o**. Older GPT models and other LLMs (e.g., Claude, Gemini) often fail or ignore instructions.
2. **Not encryption**: This is pure steganography. No cryptographic strength—just secrecy through invisibility, a human with basic knowledge of cyphers can decode the messages with a moderate sample size and a few hours.
3. **LLM instability**: LLMs are frequently updated. What works today might break tomorrow. Your mileage will vary. Future projects will attempt to address this.
4. **Detectability**: Anyone who knows what zero-width characters are—and how to extract them—can find the existence of the message.

## Final Note
This project is about exploring the boundaries of Prompt Engineering and AI-based covert communications, not creating a foolproof realworld ready system. 
