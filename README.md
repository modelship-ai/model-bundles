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

### asr/parakeet

| File | Upstream source | sha256 |
|---|---|---|
| `sherpa-onnx-nemo-parakeet-tdt-0.6b-v3-int8-1495e91b.tar.bz2` | k2-fsa/sherpa-onnx `asr-models`, `sherpa-onnx-nemo-parakeet-tdt-0.6b-v3-int8.tar.bz2` (2026-11-07) | `1495e91b59d7fc53ddca91f3431758ec99f8fa253fdb0e1e851be0f72b14b0f9` |

### asr/nemotron

| File | Upstream source | sha256 |
|---|---|---|
| `sherpa-onnx-nemotron-3.5-asr-streaming-0.6b-160ms-int8-2026-06-11-a81909a1.tar.bz2` | k2-fsa/sherpa-onnx `asr-models`, `sherpa-onnx-nemotron-3.5-asr-streaming-0.6b-160ms-int8-2026-06-11.tar.bz2` (2026-07-09) | `a81909a1780d84cff16d73c15e13e67d9d81d8839faf14870d507d8499f7a61a` |

### vad/silero

| File | Upstream source | sha256 |
|---|---|---|
| `silero_vad_v5-6b99cbfd.onnx` | k2-fsa/sherpa-onnx `asr-models`, `silero_vad_v5.onnx` (2024-07-01) | `6b99cbfd39246b6706f98ec13c7c50c6b299181f2474fa05cbc8046acc274396` |

## Licences

Each bundle keeps its upstream `LICENSE` file (Apache-2.0 for Kokoro). Bundles
also contain third-party data under its own licence: espeak-ng data
(GPL-3.0-or-later) and, in the multi-lang bundle, a jieba dictionary (MIT).
Silero VAD is MIT-licensed (snakers4/silero-vad). Parakeet TDT 0.6b v3 is
NVIDIA's model (nvidia/parakeet-tdt-0.6b-v3), licensed CC-BY-4.0; the
sherpa-onnx project made the ONNX export, and the bundle's README states both.
Nemotron 3.5 ASR streaming 0.6b is NVIDIA's model
(nvidia/nemotron-3.5-asr-streaming-0.6b), licensed OpenMDW-1.1; the sherpa-onnx
project made the ONNX export, and the bundle's README names the source model.

