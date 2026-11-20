# GitHub PR status emoji

Five custom emoji for pull request states, for Slack (or anywhere that takes custom emoji). Each one uses GitHub's own icon and colour for that state, and they read well on light and dark themes.

<img alt="The five emoji on light and dark backgrounds: draft, open, queue, merged, closed" src="preview.png" width="600" />

There's also a badge style in [`badge/`](badge/), with the icon cut out of a coloured tile. It uses the same names, so pick one style per workspace:

<img alt="Badge style of the five emoji on light and dark backgrounds" src="preview-badge.png" width="600" />

| Emoji | Name | State |
| --- | --- | --- |
| <img src="emoji/gh-pr-open.png" width="32" alt=""> | `:gh-pr-open:` | Open |
| <img src="emoji/gh-pr-draft.png" width="32" alt=""> | `:gh-pr-draft:` | Draft |
| <img src="emoji/gh-pr-queue.png" width="32" alt=""> | `:gh-pr-queue:` | In the merge queue |
| <img src="emoji/gh-pr-merged.png" width="32" alt=""> | `:gh-pr-merged:` | Merged |
| <img src="emoji/gh-pr-closed.png" width="32" alt=""> | `:gh-pr-closed:` | Closed without merging |

The names end in the values of the `{status}` token in the [Copy GitHub Link](https://github.com/jeffhandley/copy-github-link) browser extension, so one link format picks the right emoji automatically (see below).

## Add them to Slack

1. Download the PNGs in [`emoji/`](emoji/) or [`badge/`](badge/) (or use **Code → Download ZIP**).
2. In Slack, open **Add emoji**: click the smiley in any message box, then **Add Emoji**, or go to `https://<your-workspace>.slack.com/customize/emoji`.
3. Upload each PNG and name it after its file, without the extension: `gh-pr-open`, `gh-pr-draft`, `gh-pr-queue`, `gh-pr-merged`, `gh-pr-closed`.

The PNGs are 128×128 with transparent backgrounds, which is what Slack expects.

## Use them with Copy GitHub Link

[Copy GitHub Link](https://github.com/jeffhandley/copy-github-link) copies formatted links from GitHub pages. Its `{status}` token produces `open`, `draft`, `queue`, `merged`, or `closed` on pull request pages, so this link format adds the matching emoji:

```json
["<default> :gh-pr-{status}: {title} (#{number})","{org}{repo}"],
["<default> {title} (#{number})","{org}{repo}"]
```

Paste the two lines into the pull request group of the extension's options page. The second line is a fallback for pages where the status can't be read (issues, discussions). Pasted into Slack, the link shows something like:

> <img src="emoji/gh-pr-merged.png" width="16" alt=":gh-pr-merged:"> Add {status} token for pull request state (#40)

> **Note:** `{status}` is proposed upstream in [jeffhandley/copy-github-link#40](https://github.com/jeffhandley/copy-github-link/pull/40). Until it's merged and released, you can load the extension from the [`pr-status-token`](https://github.com/christopherjpaine/copy-github-link/tree/pr-status-token) branch: clone it, open `chrome://extensions`, turn on Developer mode, and choose **Load unpacked** on the `source` folder.

## License

MIT. The icon shapes are [GitHub Octicons](https://github.com/primer/octicons) (MIT), recoloured. See [LICENSE](LICENSE).
