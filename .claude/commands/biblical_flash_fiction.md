Write a draft short story in the style of the "Luke" and "Matt" flash fictions on this blog. These are ironic retellings of the Sunday gospel readings for a given Sunday in the Catholic liturgical year.

## Instructions

1. **Find the gospel reading**: Look up the Catholic lectionary gospel reading for the upcoming Sunday (or the Sunday specified by the user). Use the USCCB calendar or Catholic liturgical resources.

2. **File naming**: Follow the blog's naming convention: `YYYY-MM-DD-book-chapter-verse.md` in the `_posts/` directory. For example: `2026-02-22-matt-4-1.md`.

3. **Title**: The title should be the book and chapter of the gospel reading (e.g., "Matt 4:1", "Luke 4:1"). The tagline field may contain the actual story title, or be left empty.

4. **Front matter**: Use this format:
   ```yaml
   ---
   published: true
   layout: post
   tagline: ""
   title: "Book Chapter:Verse"
   tags:
   - allegory
   - fiction
   - religion
   ---
   ```

5. **Style guidelines**:
   - Read the existing flash fiction posts first (especially `luke-4-1.md`, `matt419.md`, and `the-old-priest.md`) to match the voice and tone.
   - The stories should **illustrate** the gospel message between the lines without being pedantic or "preachy."
   - They should **not undermine** the gospel message, but the illustration is allowed to be subtle and ironic.
   - The author is a faithful Catholic who feels no pressure to keep up appearances of saintliness.
   - Use the `<!-- more -->` excerpt separator after the first 1-3 paragraphs.
   - Aim for 400-1500 words.
   - Techniques that work well: inversions (telling it from the "wrong" perspective), modern recontextualization, extended metaphor, dialogue-driven scenes, ironic endings.
   - The prose should be literary but not purple. Concrete, sensory, grounded.
   - Endings should land with ironic clarity or quiet ambiguity — never with explanation.

6. **Reference posts for style**:
   - `_posts/2022-03-06-luke-4-1.md` — Temptation retold as a tech billionaire accepting every offer from his accountant in the West Texas desert. The "Engineer" is a failed Christ figure.
   - `_posts/2019-10-03-matt419.md` — "Fishers of men" retold from a demon's perspective, trophy-fishing for souls. Intimate, sinister, seductive.
   - `_posts/2019-10-13-the-old-priest.md` — Communion scene told in one dense paragraph. Second-person sensory immersion. A young woman's irreverent kneeling restores an old priest's soul.

## Sunday Selection

The argument specifies which Sunday to generate the story for. Examples:
- `next sunday` or no argument — use the upcoming Sunday from today's date
- `2026-03-01` — use the Sunday on that specific date
- `3rd Sunday of Lent` — use that liturgical Sunday
- `march 1` — use the Sunday on or nearest to that date

$ARGUMENTS
