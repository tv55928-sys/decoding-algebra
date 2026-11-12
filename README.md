# Algebra Decoder

A professional-learning web app for teaching Grade 9 students to **decode algebraic expressions**: to read an expression's symbols, structure and meaning before manipulating it. Built for Ontario's de-streamed Grade 9 math course (MTH1W, expectations C1.3, C1.4 and B2.2) and grounded in 15 research sources.

It is a single static page with no build step required to run and no server or data collection.

## What's inside

| Tab | For | What it does |
|---|---|---|
| **Start** | Teachers | What decoding is, why to teach it explicitly, how to use the app, curriculum links. |
| **Language** | Teachers | Precise teacher talk (e.g., "add to zero" instead of "cancel"), vocabulary teaching moves, word cards to use with students, signal words. |
| **Teach the routine** | Teachers | Six mini-lessons, one per step of the routine (Scan, Split, Spot, Say, Show, Substitute), each with a think-aloud script, questions, look-fors and misconceptions to watch for. |
| **Model it** | Teachers (projectable) | Type any expression to get a colour-coded decoding, an expression tree, three readings aloud, algebra tiles, a table, a graph and step-by-step substitution. Yellow *Teaching moves* boxes are tailored to the expression, and there's a copyable mini-lesson plan. **Student view** hides the teacher notes for projecting. |
| **Respond** | Teachers | Twelve common decoding errors with causes and teaching moves, plus eight scenarios for rehearsing responses. |
| **Practice** | Students | Eight activities with feedback: Say it right, Write it, Spot the part, Find the error, Same or different?, Match the tiles, Build it, Word check. |
| **Research** | Teachers | Each source: what it found, what it means for teaching, and where it appears in the app. |

### Student page

Add `#student` to the app's address to open a student-only page with just the Practice activities (no teacher tabs). It includes a **Return to teacher page** button.

```
https://<your-username>.github.io/algebra-decoder/#student
```

## Run it

Open `index.html` in a browser. That's it.

## Publish with GitHub Pages

1. Create a new repository on GitHub and push these files (see below).
2. In the repository, go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, pick `main` and `/ (root)`, and save.
4. After a minute the app is live at `https://<your-username>.github.io/<repository-name>/`.

```bash
git init
git add .
git commit -m "Algebra Decoder"
git branch -M main
git remote add origin https://github.com/<your-username>/algebra-decoder.git
git push -u origin main
```

## Edit and rebuild

`index.html` is generated from the files in `src/`. Edit those, then rebuild:

```bash
python3 build.py          # writes index.html
node tests/engine.test.js # checks the expression engine
```

| File | Contents |
|---|---|
| `src/shell.html` | Page structure for every tab (with placeholders the build fills in) |
| `src/practice-section.html` | The Practice tab's markup |
| `src/style.css` | All styles, light and dark themes |
| `src/engine.js` | Expression engine: parser, part roles, readings aloud, polynomials, equivalence, substitution steps (no DOM; works in Node) |
| `src/ui.js` | Interface: Model it panels, Practice activities, Language, Research, routing |
| `src/teacher.js` | Teacher layer: teaching moves, lesson plans, the six lessons, misconceptions, scenarios |

The page loads fonts from Google Fonts (Atkinson Hyperlegible, Bricolage Grotesque, STIX Two Text). Without a connection it falls back to system fonts.

## Research

See [`docs/RESEARCH.md`](docs/RESEARCH.md) for the full reading list, key findings and how each source shaped the app. Some sources were reviewed from abstracts and published summaries; the list notes which.

## Licence

No licence has been chosen yet. Add a `LICENSE` file before sharing or accepting contributions. For classroom materials, Creative Commons (e.g., CC BY-NC-SA 4.0) and MIT for the code are common choices.
