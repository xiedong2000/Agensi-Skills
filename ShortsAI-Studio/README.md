# ShortsAI-Studio Skills

A collection of reusable AI agent skills for planning, optimizing, and producing YouTube Shorts.

These skills are designed to help creators turn raw video footage, descriptions, and transcripts into engaging short-form content and polished videos.

## Skills

### 1. YouTube Shorts Content Strategist

**Location:** `skills/youtube-shorts-content-strategist/`

Helps creators develop engaging publishing content for YouTube Shorts.

Capabilities:
- Generate compelling, click-worthy video titles
- Create opening hooks to capture viewer attention
- Write concise descriptions
- Recommend relevant hashtags
- Suggest timed on-screen text
- Generate thumbnail text
- Provide creative direction and music recommendations

**Best for:** Creators who want to improve storytelling, viewer engagement, and publishing content.

### 2. YouTube Shorts Production Assistant

**Location:** `skills/youtube-shorts-production-assistant/`

Provides technical guidance and assistance for producing actual YouTube Shorts videos.

Capabilities:
- Inspect video files and identify technical properties
- Generate synchronized subtitles using speech transcription
- Prepare vertical 9:16 video formats
- Add subtitles and timed text overlays
- Mix background music with original audio
- Render videos using FFmpeg
- Validate the final video output

**Best for:** Creators who want to automate or streamline video editing and production.

Actual execution requires an environment with the appropriate file access, Python dependencies, FFmpeg, and transcription tools.

## Project Structure

```text
ShortsAI-Studio/
├── README.md
├── skills/
│   ├── youtube-shorts-content-strategist/
│   │   └── SKILL.md
│   └── youtube-shorts-production-assistant/
│       └── SKILL.md
└── examples/
```

## How to Use

1. Select the skill that matches your task.
2. Provide your video file, description, or transcript as appropriate.
3. Specify your desired style, audience, and creative preferences.
4. Review the generated content or production recommendations.
5. Refine the output before publishing.

The two skills can also be used together: first develop the content strategy, then use the production assistant to prepare the video.

## Design Principles

- Authentic and engaging storytelling
- Strong hooks and concise messaging
- Accurate descriptions without invented details
- Practical production workflows
- Reusable instructions for AI agents
- Human review and creative control

## License

MIT License. See the repository's LICENSE file for details.

## Author

Created by Dong Xie.

GitHub: https://github.com/xiedong2000/Agensi-Skills