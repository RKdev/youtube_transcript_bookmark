# YouTube Transcript Bookmarklet

Grab a YouTube video's transcript straight from the page. It works for any video that has a **Show transcript** button: no service, no daily limits, no AI. It copies the text to your clipboard and downloads it as a `.txt` file named after the video.

## Installing it

1. **Show the bookmarks bar:** `Ctrl+Shift+B` (`Cmd+Shift+B` on Mac) in Chrome, Edge or Firefox.
2. **Add a bookmark:** right-click an empty spot on the bar and choose **Add page...** (Chrome/Edge) or **Add Bookmark...** (Firefox).
3. **Fill it in:**
   - **Name:** `YT Transcript` (or whatever you like)
   - **URL:** paste the whole code block above, from `javascript:` to the final `;`
4. **Save.**

**Safari:** you can't type a URL when creating a bookmark. Bookmark any page first, then right-click it, choose **Edit Address**, and paste the code.

> Don't paste the code into the address bar. Browsers strip the `javascript:` prefix when you do that. Use the bookmark's URL field.

## Using it

1. Open a YouTube video.
2. Expand the description (**...more**), scroll down, and click **Show transcript**.
3. Click the **YT Transcript** bookmark.
4. Choose **OK** for timestamps or **Cancel** for plain text.

The transcript is copied to your clipboard and downloaded as a `.txt` file.

## Troubleshooting

- **"Open the transcript panel first" while the panel is open:** YouTube probably renamed its page elements. Right-click a transcript line, choose **Inspect**, find the new element and class names, and update `ytd-transcript-segment-renderer`, `.segment-timestamp` and `.segment-text` in the code.
- **No "Show transcript" button:** the video has no captions, not even auto-generated ones. There's nothing to grab.
- **Clipboard copy fails silently:** some browsers block clipboard writes from bookmarklets. The `.txt` download still works.

```bash
yt-dlp --skip-download --write-auto-subs --sub-langs en --sub-format vtt "VIDEO_OR_PLAYLIST_URL"
```
