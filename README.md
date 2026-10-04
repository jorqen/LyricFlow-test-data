# LyricFlow test audio

Source: recordings of church services on 24 and 27 September 2026, supplied for LyricFlow testing. Public distribution of these audio files is authorized by the contributor. No broader copyright license for the recorded performances has been established. The source-code license does not apply to this audio. No transcript or expected display has been certified. September 27 recordings contain input losses before the saved WAV; WAV time is not live wall time.

Download audio from the versioned Releases. `audio.json` describes the files; `SHA256SUMS` verifies their bytes. Originals and excerpts use mono 16 kHz 32-bit float WAV. Excerpt boundaries are integer samples in their original WAV. No code, song library, Bible snapshot or application settings are included.

## Checks and manual releases

This repository has no GitHub Actions workflows. Pushes and pull requests do not
download recordings or run the LyricFlow corpus. Validate metadata locally with
`python3 -m json.tool audio.json > /dev/null`; after downloading a selected asset,
compare `sha256sum <filename.wav>` with its entry in `SHA256SUMS` and `audio.json`.
Publish versioned audio Releases manually when needed.

Any future Actions workflow must use only `workflow_dispatch`, for a release or
a short check unavailable locally. Long runs and large corpus jobs belong in
the local LyricFlow environment. Before publishing a migration PR, use
`[skip ci]` in its HEAD commit message to avoid old `push`/`pull_request` jobs;
leave branch protection and required checks unchanged.
