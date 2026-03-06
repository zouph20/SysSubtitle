# Privacy Policy — SysSubtitle

**Last Updated: March 5, 2026**

## Overview

SysSubtitle is a real-time speech-to-text translation app for iOS. This policy explains how the app handles your data.

## Audio Data

SysSubtitle captures audio in two modes:

- **Broadcast Mode**: Captures system audio (podcasts, videos, calls) via iOS Screen Broadcasting.
- **Microphone Mode**: Captures ambient audio through the device microphone.

Audio is processed in real-time for speech recognition and is **not stored on our servers**. Audio data is sent directly to third-party speech recognition services for processing and is not retained after the session ends.

If you enable the "Save Recording" option, audio files are stored **locally on your device only** and are never uploaded without your explicit action.

## Third-Party Services

The app uses the following third-party APIs to provide its core functionality:

| Service | Purpose | Data Sent |
|---------|---------|-----------|
| Deepgram | Speech recognition | Audio stream |
| DeepL | Translation | Recognized text |
| Google Translate | Translation | Recognized text |
| OpenAI (GPT) | Text correction | Audio / text |
| Google (Gemini) | Text correction | Audio / text |
| Anthropic (Claude) | Translation & correction | Text only |

Each service processes data according to its own privacy policy. We encourage you to review their respective policies.

## Data Storage

- **API Keys**: Stored locally on your device using UserDefaults. Never transmitted to us.
- **Session Archives**: Stored locally on your device. You can delete them at any time from the app's settings.
- **Recordings**: Stored locally on your device. You can delete them at any time.

## Data We Do NOT Collect

- We do not collect personal information.
- We do not track your usage or behavior.
- We do not use analytics or advertising SDKs.
- We do not store or transmit your audio, transcriptions, or translations to our own servers.
- We do not share your data with any party other than the third-party services listed above, which are necessary for the app to function.

## Permissions

| Permission | Reason |
|------------|--------|
| Microphone | Required for microphone mode audio capture |
| Speech Recognition | Required for Apple Speech recognition engine |
| Screen Recording | Required for system audio capture via Broadcast Extension |

## Children's Privacy

This app is not directed at children under 13. We do not knowingly collect data from children.

## Changes

We may update this policy from time to time. Changes will be reflected by updating the "Last Updated" date above.

## Contact

If you have questions about this privacy policy, please contact us at: **zouph20@gmail.com**
