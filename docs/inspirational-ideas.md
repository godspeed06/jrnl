<!--
Copyright © 2012-2023 jrnl contributors
License: https://www.gnu.org/licenses/gpl-3.0.html
-->

# Inspirational Ideas

Three collections to get more out of `jrnl`: prompts to write *with*, ideas for
the project itself, and ideas for making these docs better.

## Journaling Prompts

A prompt is just a starting line. Type it, answer it, and let the answer run
longer than you planned.

```sh
jrnl today: What did I notice today that I'd normally walk past? @prompt
```

Tag every prompted entry with `@prompt` and you can separate them from your
day-to-day logging later:

```sh
jrnl @prompt -n 5
```

If you write best in an editor, keep a prompt file and open it with a
[template](./advanced.md):

```sh
jrnl --template prompts.md
```

### Reflection

- What did today teach me that yesterday's version of me didn't know?
- What did I avoid today, and what was I protecting myself from?
- Which small decision today mattered more than it looked?
- What would I tell myself a year ago about this week?
- What am I pretending not to know?
- Where did I show up as the person I want to be?

### Gratitude and good days

- Who made my day easier today, and did I tell them?
- What went well that I had no hand in?
- Three things that worked today, however small.
- What did I enjoy so much that I forgot the time?

### Work and craft

- What did I ship, and what did it cost me?
- What problem did I solve today that I couldn't solve last month?
- Which meeting could have been an entry?
- What am I the bottleneck for?
- What did I learn from someone better at this than me?

### Relationships

- Who have I been meaning to reach out to?
- What conversation am I overdue for?
- When did someone surprise me recently?
- Who am I taking for granted?

### Ideas and curiosity

- What did I read, watch, or hear that I want to steal from?
- What question has been circling my head this week?
- If I had a free weekend and no obligations, what would I build?
- What's the smallest version of the big thing I keep postponing?

### Looking forward

- What do I want next month to feel like?
- What will I stop doing?
- What's one thing I could finish before the end of the week?
- If nothing changes, where will I be in a year?

!!! tip
    Keep a running file of prompts and pick one at random each morning:

    ```sh
    jrnl today: $(shuf -n 1 ~/.local/share/jrnl/prompts.txt) @prompt
    ```

    Or let an existing entry remind you — see [Display random
    entry](./tips-and-tricks.md) for the trick.

## Feature Ideas for `jrnl`

Ideas worth exploring, all built on things `jrnl` already does well.

- **Prompt packs.** Ship a handful of prompt collections as installable
  templates, so `jrnl --template gratitude.md` works out of the box.
- **Streaks and summaries.** A built-in "how much did I write this month"
  report, so the `wc -w` recipes on [Tips and
  Tricks](./tips-and-tricks.md) aren't required.
- **A prompt picker.** A flag that picks a random line from a prompt file and
  drops it into the entry title.
- **Mood and rating.** Tags already carry `@mood:happy`-style data — a documented
  convention plus `--tags` rollups would make it a first-class habit.
- **Saved searches.** Named date-and-tag filters you can call by name instead of
  retyping ranges.
- **Static HTML export.** Turn a selection of entries into a private, readable
  site — a natural companion to the existing
  [formats](./formats.md).
- **Git-friendly journals.** Clear guidance and helpers for keeping an encrypted
  journal in a repository, building on [Privacy and
  Security](./privacy-and-security.md).
- **Imports from other journaling apps.** Day One and Obsidian are the two most
  requested neighbours.
- **A weekly review command.** Pull the last seven days, grouped by tag, as a
  single "what happened" digest.

## Ideas for These Docs

- **Journaling 101.** A short, friendly page for people who have never kept a
  journal, before they ever meet the command line.
- **A prompt library.** Grow this page into a searchable collection of prompts,
  one page per theme.
- **A recipes gallery.** Expand [Tips and Tricks](./tips-and-tricks.md) into
  short, copy-pasteable recipes with a screenshot or recording for each.
- **A FAQ.** The questions that keep coming up on GitHub issues and chat:
  where files live, how to sync, what happens if I forget my password.
- **Annotated examples.** Real (anonymised) journals showing what tags, multiple
  journals, and exports look like after a few months of use.
- **Translations.** Keep the structure stable and invite translations of the
  [User Guide](./usage.md).
