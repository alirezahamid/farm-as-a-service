# Contributing to FaaS

Thanks for helping. This guide is written by people who have done the work.

## The one rule

**Share real experience or cite a source. No guesses.**

- "I keep 6 hens and spend about £9 a month on feed" is good.
- "Hens cost about £9 a month (source: link)" is good.
- "Hens are probably cheap" is not.

If you are not sure of a fact, do not guess. Write this instead:

```markdown
<!-- TODO: needs source -->
```

A visible gap is better than a wrong number. Someone else will fill it.

## Style

- Plain English. Short sentences. No fluff.
- Jokes go in headings and the README. The advice stays serious.
- Give numbers with units and a year. "£250 for a nuc of bees (UK, 2024)".
- Say where you are. A cost in rural Wales is not a cost in California.
- Keep `docs/` general. Country rules go in `countries/<code>/`.
- Metric first. Add imperial in brackets if it helps.

## How to add a guide page

Guide pages cover one thing you can grow or keep. They live in
`docs/03-first-things/`.

1. Copy `templates/guide-page.md` to `docs/03-first-things/<name>.md`.
2. Fill in every section. Keep the headings as they are.
3. Add your sources at the bottom. "Own experience, 3 years, 12 hens,
   Scotland" counts as a source.
4. Add a link to your page in the README table.
5. Open a pull request.

## How to add a country folder

1. Find your two-letter country code (ISO 3166-1 alpha-2, lowercase).
   Example: `de`, `fr`, `us`, `nz`. We use `uk` for the United Kingdom.
2. Create `countries/<code>/README.md`.
3. Use `countries/uk/README.md` as a model. Cover subsidies, planning or
   zoning rules, animal registration, selling rules, and useful links.
4. Link to official sources. Laws change. A link ages better than a summary.
5. Add your country to the list in `countries/README.md` and the main README.
6. Open a pull request.

More detail in [countries/README.md](countries/README.md).

## How to add a story

Stories are short posts from people who moved from tech to farming, part time
or full time. Failures are welcome. They are often the most useful.

1. Copy `templates/story.md` to `docs/07-stories/<year>-<short-name>.md`.
2. Write 300 to 800 words. Include real numbers where you can.
3. It must be your own story. No invented stories.
4. Add a link in `docs/07-stories/README.md`.
5. Open a pull request.

## How to fix a fact

1. Open a "Fix a fact" issue, or go straight to a pull request.
2. Say what is wrong, what is right, and where your number comes from.

## Pull request checklist

- [ ] Every number comes from my own experience or a linked source.
- [ ] Unsure facts are marked `<!-- TODO: needs source -->`.
- [ ] Guide pages use the template headings.
- [ ] Country-specific content is in `countries/<code>/`.
- [ ] Jokes are in headings only.

## License

By contributing, you agree that your content is licensed under
[CC BY-SA 4.0](LICENSE).
