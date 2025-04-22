# Chinese-LiPS: A Chinese audio-visual speech recognition dataset with Lip-reading and Presentation Slides

[![Hugging Face Datasets](https://img.shields.io/badge/🤗%20Hugging%20Face-Datasets-yellow.svg)](https://huggingface.co/datasets/BAAI/Chinese-LiPS)   [![License: CC BY-NC-SA-4.0](https://img.shields.io/badge/License-CC%20BY--SA--NC%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)   [![GitHub Pages](https://img.shields.io/badge/GitHub-Pages-blue.svg)](https://kiri0824.github.io/Chinese-LiPS/)

## ⭐ Introduction

The **Chinese-LiPS** dataset is a multimodal dataset designed for audio-visual speech recognition (AVSR) in Mandarin Chinese. This dataset combines speech, video, and textual transcriptions to enhance automatic speech recognition (ASR) performance, especially in educational and instructional scenarios.

## 🚀 Dataset Details

- **Total Duration:** 100.84 hours
- **Number of Speakers:** 207 professional speakers
- **Number of Clips:** 36,208 video clips
- **Audio Format:** Stereo WAV, 48 kHz sampling rate
- Video Format:
  - **Slide Video:** 1080p resolution, 30 fps
  - **Lip-Reading Video:** 720p resolution, 30 fps
- **Annotations:** JSON format with transcriptions and extracted text from slides

### Dataset Statistics

| Split      | Duration (hrs) | # Segments | # Speakers |
| ---------- | -------------- | ---------- | ---------- |
| Train      | 85.37          | 30,341     | 175        |
| Validation | 5.35           | 1,959      | 11         |
| Test       | 10.12          | 3,908      | 21         |
| **Total**  | **100.84**     | **36,208** | **207**    |

## 📂 Dataset Organization

The dataset is structured into several compressed files:

- **image.zip**: First-frame images from slide videos (used for OCR and vision-language models).

- **pptdataset.zip**: Processed data with 16 kHz audio, 96×96 25-frame lip-reading videos, and JSON annotations.

- train.zip, test.zip, val.zip: Data split into training, testing, and validation sets. Each contains:

  ```
  ├── ID1_age_gender_topic/
  │   ├── WAV/
  │   │   ├── ID1_age_gender_topic_001.json  # Annotation file
  │   │   ├── ID1_age_gender_topic_001.wav   # Audio file (48 kHz)
  │   ├── PPT/
  │   │   ├── ID1_age_gender_topic_001_PPT.mp4  # Slide video (1080p 30fps)
  │   ├── FACE/
  │   │   ├── ID1_age_gender_topic_001_FACE.mp4  # Lip-reading video (720p 30fps)
  ├── ...
  ```

- **meta_all.csv, meta_train.csv, meta_valid.csv, meta_test.csv**: Metadata files with ID, TOPIC, WAV, PPT, FACE, and TEXT fields.

  The TOPIC field is abbreviated in Chinese as follows: DZJJ = E-sports & Gaming, JKYS = Health & Wellness, KJ = Science & Technology, LY = Travel & Exploration, QC = Automobile & Industry, RWLS = Culture & History, TY = Sports & Competitions, YS = Movies & TV Series, ZX = Others.

- **meta_test.json**: Includes OCR and InternVL2 prompts for the test set.

  ```
  wav_path: Path to the audio file.
  ppt_path: Path to the first-frame image of the slide video.
  ocr_text: Text extracted by PaddleOCR.
  vl2_text: Text extracted by InternVL2.
  gt_text: Ground truth transcription of the audio.
  ocr_vl2_text: OCR text reprocessed by InternVL2 (not a concatenation of PaddleOCR and InternVL2 results).
  ```

## 📥 Download

You can download the dataset from the following sources:

- [Download from OneDrive](https://1drv.ms/f/c/721006f535f6400c/EgxA9jX1BhAggHI-hgAAAAABgpJYJF-leYBGBdmjBuBQxw)
- [Download from Huggingface](https://huggingface.co/datasets/BAAI/Chinese-LiPS)
- [Download from Baidu Netdisk](https://pan.baidu.com/s/11nvn79-3Inf3QDyJomlLAA?pwd=vg2a) (Password: **vg2a**)

## 📚 Citation

```bibtex
@misc{zhao2025chineselipschineseaudiovisualspeech,
  title={Chinese-LiPS: A Chinese audio-visual speech recognition dataset with Lip-reading and Presentation Slides}, 
  author={Jinghua Zhao and Yuhang Jia and Shiyao Wang and Jiaming Zhou and Hui Wang and Yong Qin},
  year={2025},
  eprint={2504.15066},
  archivePrefix={arXiv},
  primaryClass={cs.MM},
  url={https://arxiv.org/abs/2504.15066}
}
