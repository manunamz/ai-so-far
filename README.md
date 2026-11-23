# ai-time

A scroll through the general history of AI, from the Mechanical Turk (1770) to today.

It opens on the "we can't feel exponentials" joke, then bends that cartoon curve into a running count of real milestones: ideas, machines, culture, work, science and society. Along the way it marks when people started saying **AI**, **AGI** and **ASI**.

## Run

It's a single static page with no build step:

```sh
open index.html
```

It needs a network connection to load [D3](https://d3js.org) 7.8.5 from cdnjs and fonts from Google Fonts. The page doesn't work without D3; fonts fall back.

## Edit

Everything is in `index.html`.

| What | Where |
| --- | --- |
| Colors and fonts | `:root` tokens at the top of `<style>` |
| Milestones | `const E` |
| Definitions of AI, AGI and ASI | `const G` |
| Model dots | `const MODELS` |
| Camera per milestone | `cam()` |

A milestone is an array, in date order:

```js
[date, title, text, sourceUrl, category, caution, marker, extraUrl1, extraUrl2]
```

- `date` is `YYYY`, `YYYY.MM` or `YYYY.MM.DD`.
- `caution` is an optional note for contested results.
- `marker` is `"AI"`, `"AGI"`, `"ASI"` or `null`. It makes the oversized card and the line on the chart.
- The two extra links are only shown on the Riemann card, where they are labelled as the Meta and Musk reactions.

Some things are written by hand and won't update themselves: the "70 years. Then 78 days." frame, the counts in the chart's `aria-label` and intro card, the start year, the compile date, and the era buttons, which find milestones by title.

## Reading the chart

- The line counts the milestones on this page. They were hand-picked, and recent ones are easier to remember, so part of the climb is selection.
- The faint dots are AI models, placed by estimated training compute on their own log scale, which rescales with each view. Their height isn't comparable with the line.
- The AI, AGI and ASI lines mark when people used each word as a claim. They don't show that AGI or ASI was reached.
- The opening cartoon isn't data.

## Sources and credits

- Model data: [Epoch AI](https://epoch.ai/data/ai-models), [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/), downloaded 2026-11-23. 546 notable models with a date and a compute estimate; some estimates are speculative.
- The cartoon is redrawn after Tim Urban's ["The AI Revolution"](https://waitbutwhy.com/2015/01/artificial-intelligence-revolution-1.html), Wait But Why, 2015.
- Each milestone card links to its source. Many older entries were written from general knowledge and their links haven't all been checked.
- Built with Claude, which is made by Anthropic. Several 2026 entries involve Anthropic or its competitors.
