<div align="center">

# K-SORI

**Korean Speech Dataset for Overall Robustness in SASV**

[![HuggingFace](https://img.shields.io/badge/🤗%20Dataset-eoil%2FK--SORI-blue)](https://huggingface.co/datasets/eoil/K-SORI)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-green.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Demo](https://img.shields.io/badge/🔊%20Audio-Demo-orange)](https://2oil.github.io/K-SORI/demo.html)

</div>

<p align="center">
  <img src="https://raw.githubusercontent.com/2oil/K-SORI/main/Contribution.png" width="85%"/>
</p>

---

## Overview

K-SORI is a large-scale **Korean** speech dataset for spoofing-aware speaker verification (SASV) research. It covers both Logical Access (LA) and Physical Access (PA) attack scenarios, with four key characteristics:

- **26 diverse attack types** — TTS, VC, speech editing, adversarial attacks, and more
- **Mixed acoustic domains** — studio recordings + real-world (AIHub, YouTube, ITW)
- **Large-scale speaker diversity** — 1,347 speakers, 3.4M+ utterances
- **Flexible AI-processed evaluation** — 9 neural processing types (codec, enhancement)

| Scenario | Description | Utterances |
|----------|-------------|:----------:|
| **LA** | TTS/VC spoofed (A01–A25) + AI-processed (P01–P09) + Bonafide | 2,819,449 |
| **PA** | Replay attacks — real rooms (R1, R2) + simulated RIRs | 593,252 |
| **Total** | 1,347 speakers | **3,412,701** |

---

## Audio Demo

> **[🔊 Listen to samples](https://2oil.github.io/K-SORI/demo.html)** — bonafide, spoofed, AI-processed, and replay samples per speaker

---

## Dataset

> **[🤗 eoil/K-SORI on HuggingFace](https://huggingface.co/datasets/eoil/K-SORI)**

```python
from datasets import load_dataset

la = load_dataset("eoil/K-SORI", "LA")
pa = load_dataset("eoil/K-SORI", "PA")
```

---

## LA Attack Types

### Spoofed (A01–A25)

| ID | Model | Category |
|----|-------|----------|
| A01 | [Zonos (v0.1-hybrid)](https://github.com/Zyphra/Zonos) | Zero-shot TTS |
| A02 | [GPT-SoVITS](https://github.com/RVC-Boss/GPT-SoVITS) | Zero-shot TTS |
| A03 | [Coqui-ai TTS](https://github.com/coqui-ai/TTS) | Zero-shot TTS |
| A04 | [Zonos (v0.1-transformer)](https://github.com/Zyphra/Zonos) | Zero-shot TTS |
| A05 | [ElevenLabs (multilingual v2)](https://elevenlabs.io/) | Commercial TTS |
| A06 | [Coqui-ai TTS](https://github.com/coqui-ai/TTS) | Zero-shot VC |
| A07 | [seed-vc](https://github.com/Plachtaa/seed-vc) | Zero-shot VC |
| A08 | [ElevenLabs (multilingual v2)](https://elevenlabs.io/) | Commercial VC |
| A09 | [Partially Fake](https://github.com/2oil/partially_fake) | Partial fake |
| A10 | [VoiceCraft](https://github.com/jasonppy/VoiceCraft) | Speech editing |
| A11 | [VITS (fine-tuned)](https://github.com/ylacombe/finetune-hf-vits) | Fully-trained TTS |
| A12 | [MeloTTS](https://github.com/myshell-ai/MeloTTS) | Fully-trained TTS |
| A13 | [OpenVoice](https://github.com/myshell-ai/OpenVoice) | Zero-shot TTS |
| A14 | [CosyVoice](https://github.com/FunAudioLLM/CosyVoice) | Zero-shot TTS |
| A15 | [Kits.ai](https://www.kits.ai/ko/) | Commercial VC |
| A16 | [VALL-E (Korean)](https://huggingface.co/LearnItAnyway/vall-e_korean) | Zero-shot TTS |
| A17 | [Chatterbox](https://github.com/resemble-ai/chatterbox) | Zero-shot TTS |
| A18 | [SSR-Speech](https://github.com/WangHelin1997/SSR-Speech) | Speech editing |
| A19 | [PartialEdit](https://github.com/ycemsubakan/speechbrain-1/tree/partial_edit) | Speech editing |
| A20 | [IMS-Toucan](https://github.com/DigitalPhonetics/IMS-Toucan) | Zero-shot TTS |
| A21 | [FAKEBOB](https://github.com/FAKEBOB-adversarial-attack/FAKEBOB) | Adversarial (ASV target) |
| A22 | [Double-deceiver](https://github.com/joanna-janos/double-deceiver) | Adversarial (SASV target) |
| A23 | A08 + A22 | Adversarial (SASV target) |
| A24 | A05 + [Malafide](https://github.com/eurecom-asp/malafide) | Adversarial (CM target) |
| A25 | [Chatterbox](https://github.com/resemble-ai/chatterbox) | Zero-shot VC |

### AI-Processed (P01–P09)

| ID | Model | Category |
|----|-------|----------|
| P01 | [BigCodec](https://github.com/Aria-K-Aleth/bigcodec) | Neural Codec |
| P02 | [EnCodec](https://github.com/facebookresearch/encodec) | Neural Codec |
| P03 | [SpeechTokenizer](https://github.com/ZhangXInFD/SpeechTokenizer) | Neural Codec |
| P04 | [FunCodec](https://github.com/alibaba-damo-academy/FunCodec) | Neural Codec |
| P05 | [AcademiCodec](https://github.com/yangdongchao/AcademiCodec) | Neural Codec |
| P06 | [Demucs](https://github.com/facebookresearch/demucs) | Speech Enhancement |
| P07 | [resemble-enhance](https://github.com/resemble-ai/resemble-enhance) | Speech Enhancement |
| P08 | [VoiceFixer](https://github.com/haoheliu/voicefixer) | Speech Enhancement |
| P09 | [ClearerVoice-Studio](https://github.com/modelscope/ClearerVoice-Studio) | Speech Enhancement |

---

## PA Conditions

116 distinct playback/recording conditions across physical and simulated environments.

| Setting | Details |
|---------|---------|
| Rooms | R1 (6.0×7.2×2.7 m), R2 (6.3×6.5×2.7 m) |
| Loudspeakers | LG gram (laptop), Sony Bluetooth speaker |
| Microphones | Logitech BRIO, IRIVER headphones, BLUE Yeti, Waycos Croad, Samsung Galaxy Book |
| Simulated | RIRs from [ReplayDF](https://huggingface.co/datasets/mueller91/ReplayDF) |

---

## Protocol Files

All protocol CSVs are in the [`protocol/`](protocol/) directory.

### Scenario Protocols

| File | Description | Rows |
|------|-------------|:----:|
| `K-SASV_LA_protocol.csv` | Full LA protocol (A00–A25, P01–P09) | 2,819,449 |
| `K-SASV_PA_protocol.csv` | Full PA protocol (real + simulated replay) | 593,252 |

### Training Protocols

#### Standard CM (A01–A25 only)

| File | Split | Rows |
|------|-------|:----:|
| `K-SASV_train.csv` | Train | 1,652,172 |
| `K-SASV_eval.csv` | Eval | 308,833 |

#### Extended — includes AI-processed speech (P01–P09)

| File | Scenario | Split | Rows |
|------|----------|-------|:----:|
| `K-SASV_train_spoofing.csv` | Spoofing detection | Train | 2,066,045 |
| `K-SASV_eval_spoofing.csv` | Spoofing detection | Eval | 528,443 |
| `K-SASV_train_deepfake.csv` | Deepfake detection | Train | 2,066,045 |
| `K-SASV_eval_deepfake.csv` | Deepfake detection | Eval | 528,443 |

**Column descriptions**

| Column | Description |
|--------|-------------|
| `speaker_norm` | Speaker ID |
| `path_audio` | Relative path to audio file |
| `age` | Speaker age group (Young / Adult / Elder) |
| `gender` | M / F |
| `recrdTime` | Recording duration (seconds) |
| `recrdEnv` | Recording environment |
| `recrdDevice` | Recording device |
| `type` | Attack type (`-`=bonafide, A01–A25, P01–P09) |
| `label` | `bonafide` / `spoof` / `AI-processed` |

---

## Pretrained Models

Models trained on K-SORI LA — available on Google Drive:

> **[📁 Google Drive — Pretrained Models](https://drive.google.com/drive/folders/1df5XEI54WAhug-su2nOGOd84q7JV7ghC?usp=sharing)**

| Model | Paper / Code |
|-------|-------------|
| AASIST | [clovaai/aasist](https://github.com/clovaai/aasist) |
| Conformer-TCM | [ductuantruong/tcm_add](https://github.com/ductuantruong/tcm_add) |

Training followed original configurations with K-SORI LA protocols as drop-in replacements.

---

## Citation

```bibtex
@dataset{k-sori,
  author    = {eoil},
  title     = {K-SORI: Korean Speech Anti-Spoofing Research Dataset},
  year      = {2026},
  url       = {https://huggingface.co/datasets/eoil/K-SORI}
}
```

---

## License

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)
