# transcriber
This repository automates transcription of audio files from URLs into timestamped JSON using the Whisper API. For each audio file, the repository stores audio and its JSON transcript in `/audio/<song-name>/`, e.g., `<audio-file>.mp3` and `<audio-file>.json`. The folder structure is:

Setup: clone or create this repo in GitHub or Codespaces, install dependencies with `pip install requests`, replace `YOUR_WHISPER_API_KEY` in `scripts/transcribe_urls.py`, and list your audio URLs in `urls.txt`, one per line:

https://example.com/song1.mp3
https://example.com/song2.mp3


Usage: run `python scripts/transcribe_urls.py` 
or 
`./run.sh`. 

The script downloads each audio file, sends it to Whisper API for transcription with word-level timestamps, and saves `.mp3` and `.json` in `/audio/<song-name>/`. Commit and push to store everything online. Notes: `audio/` subfolders are created automatically, each JSON contains segment start/end, full text, and word timestamps. Optional: use GitHub Actions for automation, add error logging or retries, or manage dependencies with `requirements.txt`.
