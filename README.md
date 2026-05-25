# call_center_audio_dual_channel_te
**Dataset Description:**

This dataset is a **large-scale collection of raw Telugu call center audio (dual-channel)**, designed to support the development and training of advanced speech and AI systems.

It consists of real-world customer and agent speech recordings collected from call center environments. The dataset is organized in a dual-channel format, where corresponding customer and agent audio are available as separate recordings, enabling clear role-based modeling and analysis.
The dataset captures authentic speech characteristics such as tone variation, pauses, silence patterns, and natural speaking behaviour commonly observed in customer service environments. This makes it highly valuable for building accurate, scalable, and production-ready AI systems for enterprise and customer support applications.
Additionally, this dataset can be used in data pipelines for **Supervised Fine-Tuning (SFT)** and **Reinforcement Learning with Human Feedback (RLHF)** workflows.

**Key Use Cases**

    -Training Automatic Speech Recognition (ASR) systems for call center environments
    -Call analytics and conversation intelligence
    -Sentiment analysis and emotion detection
    -Quality monitoring and compliance analysis
    -Virtual assistants for customer support
    -Speech-to-Text (STT) for structured call transcription

**Dataset Specification**

    -Language: Telugu
    -Type: Raw, unprocessed call center audio
    -Speech Style: Customer and agent speech from call center environments
    -Audio Conditions: Real-world call center environments
    -Domains: customer support, service calls, query resolution, etc.
    -Channel Configuration: Dual-channel (separate customer and agent recordings)
    -Format: .wav, .mp3, .ogg, etc.
    -Sampling Rate: 8000 Hz
    -Duration: 12,304 hours

**Value of Dual Channel Dataset**

    -Clear separation of customer and agent speech for accurate modeling
    -Supports role-based speech analysis and modeling
    -Improves performance in real-world customer support scenarios
    -Ideal for call center analytics and conversation intelligence systems
    -Facilitates precise annotation and labeling workflows


    
**Audio Quality Analysis**


Signal Quality Analysis (Signal QA)

To ensure robust signal-level integrity and consistency, the dataset was evaluated using multiple acoustic and signal-processing metrics.

| Metric                    | Value      | Interpretation                                                                  |
| ------------------------- | ---------- | ------------------------------------------------------------------------------- |
| **Average SNR (dB)**      | **50.03**  | High signal-to-noise ratio indicating clean audio with minimal background noise |
| **Average RMS Energy**    | **0.089**  | Stable signal energy level, suitable for speech processing tasks                |
| **Silence Ratio**         | **0.448**  | reflects natural conversational pauses                                          |
| **Clipping Ratio**        | **0.0**    | No clipping detected, ensuring distortion-free audio                            |
| **Loudness (LUFS)**       | **-22.12** | Well-balanced loudness within acceptable range for speech datasets              |
| **Overall Quality Score** | **70.83**  | Good signal quality, appropriate for training and evaluation pipelines          |


 DNSMOS Evaluation

To ensure production-level reliability, the dataset was evaluated using DNSMOS (Deep Noise Suppression Mean Opinion Score) out of 5 is.

| Metric                 | Score    | Interpretation                                            |
| ---------------------- | -------- | --------------------------------------------------------- |
| Speech Quality (SIG)   | **3.89** | Clear and intelligible conversational speech              |
| Background Noise (BAK) | **4.01** | Strong noise suppression with stable acoustic clarity     |
| Overall MOS (OVR)      | **3.81** | High-quality real-world audio suitable for model training |


**SQUIM-Based Audio Quality Analysis**

To further assess perceptual and signal characteristics, the dataset was evaluated using SQUIM-based metrics.


| Metric                       | Value     | Interpretation                                                              |
| ---------------------------- | --------- | --------------------------------------------------------------------------- |
| **Average Energy**           | **0.003** | Low energy level, indicating controlled signal amplitude without distortion |
| **Spectral Flatness**        | **0.052** | Low flatness suggests speech-dominant signal (not noise-like)               |
| **Zero Crossing Rate (ZCR)** | **0.062** | Low ZCR, consistent with voiced speech and minimal high-frequency noise     |
| **Dynamic Range**            | **1.683** | Moderate variation in amplitude, capturing natural speech dynamics          |
| **SI-SDR Proxy**             | **15.0**  | Good signal-to-distortion ratio, indicating clear and well-separated speech |
| **SQUIM Score**              | **62.59** | Solid perceptual quality, suitable for real-world speech applications       |



Key Insight

The dataset maintains strong acoustic quality despite real-world conditions, making it suitable for production-grade AI systems, LLM pipelines, and speech understanding models.


**Dataset Validation via End-to-End Model Training**

To validate dataset effectiveness, a complete speech-to-NLP training pipeline was built and executed using InfoBay.AI Audio dataset

**Full Pipeline**

Raw podcast audio
→ OpenAI Whisper transcription
→ Sentiment labeling
→ DistilBERT training (from scratch)
→ 3-class sentiment classification

  Validation Insight

   This end-to-end workflow demonstrates that the dataset is not only large-scale but also self-sufficient for training downstream AI models without reliance on external pretrained datasets.


**Sentiment Classification Task**

The dataset supports supervised learning for sentiment understanding across three classes:

    Negative (Class 0)
    Neutral (Class 1)
    Positive (Class 2)

The dataset contains naturally occurring emotional and contextual variation, making it highly suitable for:

    RLHF preference modeling
    Emotion-aware conversational agents
    Human-aligned response generation systems



**Model Performance (From-Scratch Training) From our Dataset**

A DistilBERT-based model trained from scratch achieved strong performance on this dataset:
    Accuracy: ~98%
    Macro F1-score: ~0.98
    Weighted F1-score: ~0.99

Classification Report

| Class | Sentiment | Precision | Recall | F1-score | Support |
| ----- | --------- | --------- | ------ | -------- | ------- |
| 0     | Negative  | 0.97      | 0.96   | 0.96     | 1,128   |
| 1     | Neutral   | 0.99      | 0.99   | 0.99     | 7,865   |
| 2     | Positive  | 0.98      | 0.98   | 0.98     | 2,658   |



**Basic JSON Schema**
```json
{
"id": "string",
"audio_filepath": "string",
"duration": "float",
"language": "string",
"sample_rate": "integer",
"format": "string",
"num_speakers": "integer",
"domain": "string",
"metadata": {
"source": "string",
"recording_condition": "string"
}
}
```
**Full Dataset Overview**

  Total Duration (in hours): 1,316,582

  This dataset is part of a large multilingual podcast audio collection covering the following languages: Arabic, Arabic(EG), Arabic(UG), Assamese, Bengali, Chinese, English (India),  English (UK), English (US), Filipino, French, Ganda, German, Gujarati, Hindi, Italian, Japanese, Kannada, Kinyarwanda, Korean, Luganda, Malay, Malayalam, Mandarin, Marathi, Mizo, Nepali, Oriya, Punjabi, Russian, Somali (SO), Somali (UG), Spanish (MX), Spanish (ES), Swahili (KE), Swahili (UG), Tamil, Telugu, Tigrinya, Urdu and Yoruba.

**Data Creation**

  Procured through formal agreements and generated in the ordinary course of business.

**Considerations**

  This dataset is provided for research and educational purposes only. It contains only sample data. For access to the full dataset and enterprise licensing options, please visit our website [InfoBay AI](https://infobay.ai/) or contact us directly.

    -Ph: (91) 8303174762
    -Email: datareq@infobay.ai
