# Cyphera — AI-Powered NSFW Content Moderation System

An AI-driven multimedia moderation system that detects NSFW/unsafe content across **audio, text, and image** inputs, built to help platforms flag harmful content automatically instead of relying purely on manual review.

## Why I built this
Content moderation at scale needs to handle more than just images — harmful content shows up in speech, text captions, and visuals together. Cyphera combines multiple specialized models into one pipeline so all three modalities are checked in a unified flow.

## How it works
- **Audio** → Transcribed using **Whisper ASR**, then passed through a text classifier for flagged content.
- **Text** → Classified using **BERT** for harmful/explicit language detection.
- **Image** → Screened using **NudeNet** for NSFW visual content.
- Each modality outputs a confidence score, which is aggregated to produce a final moderation decision.

## Results
- Achieved **~90% detection accuracy** across test data.
- Evaluated using **precision, recall, and F1-score** to balance false positives (over-flagging) against false negatives (missed content).

## Tech Stack
- **Languages:** Python
- **Libraries/Models:** PyTorch, TensorFlow, OpenCV, Whisper ASR, BERT, NudeNet

## How to Run
```bash
# Clone the repo
git clone https://github.com/Tanisha24-hub/Cyphera.git
cd Cyphera

# Install dependencies
pip install -r requirements.txt

# Run the moderation pipeline
python main.py --input <path_to_file>
```
*(Update the commands above to match your actual entry point and setup steps.)*

## Project Structure
```
Cyphera/
├── audio/          # Whisper ASR transcription + classification
├── text/           # BERT-based text classification
├── image/          # NudeNet-based image screening
├── main.py         # Entry point
└── requirements.txt
```

## Future Improvements
- Add a web-based demo interface
- Support video input by extracting frames + audio separately
- Expand evaluation to a larger, more diverse dataset
