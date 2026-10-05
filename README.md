# model-bundles

Unmodified copies of third-party model bundles that
[modelship](https://github.com/modelship-ai/modelship) downloads at deploy time.

modelship pins each bundle by its sha256. Upstream projects sometimes replace a
release file in place, which breaks that pin for every installed version. The
copies here never change, so a modelship release keeps working.

## Layout

Bundles are release assets, not files in the git tree. Each model family has
one release, and its tag reads like a path:

    https://github.com/modelship-ai/model-bundles/releases/download/tts/kokoro/<file>

A file name ends with the first 8 characters of the file's sha256.

## Rules

- A published file is never replaced or deleted.
- A new version of a bundle is a new file with a new name.
- Files are uploaded exactly as upstream published them, never repacked.

## Contents

### tts/kokoro

| File | Upstream source | sha256 |
|---|---|---|
| `kokoro-multi-lang-v1_0-c5f7e2d2.tar.bz2` | k2-fsa/sherpa-onnx `tts-models`, `kokoro-multi-lang-v1_0.tar.bz2` (2026-09-08) | `c5f7e2d2caf082bc1d20fb70334a61d99d20b484500aad32e7cf84c128ea3298` |
| `kokoro-en-v0_19-91280485.tar.bz2` | k2-fsa/sherpa-onnx `tts-models`, `kokoro-en-v0_19.tar.bz2` (2025-08-10) | `912804855a04745fa77a30be545b3f9a5d15c4d66db00b88cbcd4921df605ac7` |

## Licences

Each bundle keeps its upstream `LICENSE` file (Apache-2.0 for Kokoro). Bundles
also contain third-party data under its own licence: espeak-ng data
(GPL-3.0-or-later) and, in the multi-lang bundle, a jieba dictionary (MIT).

