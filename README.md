# தமிழ் மேற்கோள்கள் (Tamil Quotes)

A simple, scalable collection of Tamil quotes stored as individual JSON files in this repository.  
This repo is designed to serve as a static quote source that can be easily fetched and used in any frontend project.

---

## Repository Structure

```
tamil-quotes/
├── quotes/
│   ├── 1.json
│   ├── 2.json
│   ├── 3.json
│   └── ...  
└── index.json
```

- Each quote is stored in its own JSON file inside the `quotes/` folder.
- `index.json` contains the total count of quotes available in the repo.

---

## JSON File Format

### `index.json`

```json
{
  "count": <number_of_quotes>
}
```

### Example quote file (`quotes/1.json`)

```json
{
  "quote": "வாழ்க்கை ஒரு பாடம், அனுபவம் ஒரு ஆசிரியர்.",
  "author": "அறியப்படாதவர்"
}
```

---

## Usage

You can fetch quotes from this repository easily using client-side JavaScript.

### Example: Fetch a random quote

```js
const baseURL = "https://mithu-vulcan.github.io/tamil-quotes-api/";

async function getRandomQuote() {
  // Fetch the total number of quotes
  const indexRes = await fetch(`${baseURL}/index.json`);
  const { count } = await indexRes.json();

  // Generate a random quote number
  const randomId = Math.floor(Math.random() * count) + 1;

  // Fetch the quote JSON file
  const quoteRes = await fetch(`${baseURL}/quotes/${randomId}.json`);
  const quoteData = await quoteRes.json();

  // Use the quote data (example: display in console)
  console.log(`${quoteData.quote} — ${quoteData.author}`);
}

getRandomQuote();
```

---

## Notes

- All the quotes were made with gpt
- Working on adding real quotes from people
- This repo serves static JSON files — no backend or server required.
- Since each quote is in its own file, the client fetches only one quote at a time, improving load performance.

---

## License

Feel free to use, modify, and distribute these quotes and code.  
Please attribute properly if you use it publicly.

---

## Contributions

Contributions of more Tamil quotes are welcome!  
To add quotes, please create a new JSON file following the existing structure and update `index.json` accordingly.

---

**Enjoy the Tamil wisdom!**
