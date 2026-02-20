# 📚 Smart PDF Study Assistant

*Because scrolling through 300 pages of lecture notes at 2 am before an exam is not it.*

## What Even Is This?

Hey! So I built this after realizing I had like 50 PDFs of lecture notes scattered everywhere and no idea what was in them. You know that feeling when your prof mentions "remember that formula from week 3?" and you're like "...which PDF was that in again?" 

Yeah. This tool fixes that.

It takes all your PDFs, reads them, finds important stuff, and creates an actual study guide. Plus it uses AI (Claude/ChatGPT) to summarize everything in a way that actually makes sense. No more ctrl+F-ing through 10 different files at midnight.

## Why I Made This

Real talk: I'm trying to build a personal AI agent that can remember everything I learn (videos, PDFs, notes, etc.) and help me actually retain information. This is one piece of that bigger puzzle.

But also... I just really needed a better way to study. Traditional note-taking wasn't cutting it, and I kept forgetting where I read important concepts. So I automated it 🤷‍♂️

## What It Does

Drop some PDFs in a folder, run the script, and get:

- 🤖 **AI-generated summary** - Claude/ChatGPT reads everything and makes a study guide
- 🔍 **Keyword analysis** - Counts how many times important terms appear
- 📊 **Most common words** - See what topics come up the most
- 📝 **Quick preview** - First chunk of your notes for context
- 💾 **Clean output file** - Everything saved in one place

Basically, it's like having a study buddy who actually reads all the material.

## Getting Started

### What You Need
```bash
# The basics
pip install pypdf

# For AI summaries (optional but highly recommended)
pip install anthropic
```

If you want to use ChatGPT instead of Claude, do `pip install openai` and tweak the code a bit.

### Setup

1. **Create your folders:**
```bash
mkdir pdf_assistant
cd pdf_assistant
mkdir pdfs output
```

2. **Put your PDFs in the `pdfs` folder**
   - Lecture notes, textbook chapters, whatever
   - Just dump them all in there

3. **Get an API key** (if you want AI summaries):
   - Claude: https://console.anthropic.com/
   - ChatGPT: https://platform.openai.com/

4. **Set your API key:**
```bash
export ANTHROPIC_API_KEY='your-key-here'
```

5. **Run it:**
```bash
python main.py
```

That's it! Check the `output` folder for your study guide.

## Example
```
============================================================
        🎓 SMART PDF STUDY ASSISTANT 🎓
============================================================

📚 Loading PDFs from 'pdfs'...

✅ Loaded: algorithms_notes.pdf (42 pages)
✅ Loaded: data_structures.pdf (38 pages)
✅ Loaded: practice_problems.pdf (15 pages)

📊 Total: 3 PDFs loaded

🔍 Searching for keywords...

  'algorithm': 67 occurrences
  'complexity': 34 occurrences
  'sorting': 28 occurrences

🤖 Generating AI summary...

✅ Study guide saved to: output/study_guide.txt

🎉 Done!
```

Then you open `study_guide.txt` and boom—everything's organized and summarized.

## Real Use Cases

**Before exams:**
- Dump all lecture PDFs into the folder
- Get a consolidated study guide in seconds
- Actually know what to focus on

**Research:**
- Load papers on a topic
- See which terms/concepts appear most
- Get a quick overview without reading 100 pages

**General learning:**
- Organise course materials
- Track important concepts
- Build a personal knowledge base

## What I Want to Add Next

- [ ] **Page references** - Show which page each concept is on
- [ ] **PDF output** - Generate the study guide as a nice PDF
- [ ] **OCR support** - Handle scanned/image-based PDFs
- [ ] **Web interface** - Maybe a simple Streamlit app?
- [ ] **Combine with my YouTube tool** - Search both PDFs and video transcripts
- [ ] **Flashcard generation** - Auto-create Anki cards from key terms
- [ ] **Graph view** - Visualize connections between concepts

If you have ideas or want to contribute, I'm all ears! Still learning and would love feedback.

## Known Issues

- **Scanned PDFs don't work** - The text needs to be selectable. If your PDF is just images, it won't extract anything. (Working on OCR support!)
- **Some PDFs have weird formatting** - Sometimes the extracted text looks messy. That's just how PDFs work, unfortunately.
- **AI summaries cost money** - Claude/ChatGPT APIs aren't free. Each summary costs like $0.01-0.05, depending on length. Still way cheaper than my coffee habit though.
- **Long PDFs take time** - Processing 500+ pages might take a minute. Grab a snack.

## Tech Stack

Pretty simple:
- **Python** - Because it's the best for this stuff
- **PyPDF** - For reading PDFs
- **Claude/ChatGPT API** - For the AI magic
- **Collections.Counter** - For word frequency (built-in, so clean)

No fancy frameworks, no bloat. Just straightforward Python that works.

## Contributing

I'm still learning, so if you see something that could be better, please let me know! Open an issue or PR. Some things that would be cool:

- Better text extraction for messy PDFs
- Support for more file types (Word docs, PowerPoints?)
- Cooler visualisations for the word frequency
- Better AI prompts for summaries
- Literally any improvements you can think of

Seriously, I'd love to collaborate and learn from you.

## Why I'm Sharing This

Honestly? Because I wish I had found something like this when I was drowning in PDFs last semester. If this helps even one person study better or organise their notes, that's a win.

Also, I'm building toward a bigger goal (that personal AI agent thing I mentioned), and sharing the journey feels right. We're all just trying to learn and build cool stuff, ya know?

## License

MIT - Do whatever you want with this. Seriously. Sell it, modify it, use it for your startup, I don't care. Just don't sue me if it accidentally deletes your notes or something (it won't, but you know, legal stuff).

If it helps you pass an exam or finish a project, that's all the credit I need 😊

## Shoutout

- **PyPDF library** - Made this project possible
- **Anthropic/OpenAI** - For the APIs that make the AI summaries work
- **My Engineering professors** - For assigning so much reading that I had to automate it
- **Coffee** - The real MVP

---

Made by a tired Engineering student who just wants to study smarter, not harder.

If this helped you, give it a ⭐ or send good vibes. Both are appreciated 🙏

**P.S.** - Check out my other project: [YouTube Quote Hunter](https://github.com/yourusername/youtube-quote-hunter) for searching video transcripts. Same energy, different use case.
