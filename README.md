# NestUI API Documentation 🧠

Welcome to the NestUI API reference. Our API allows you to integrate state-of-the-art AI generation directly into your own applications. 

## 🌍 Global API Concepts

**Base URL (Production):**
All API requests should be made to the live environment endpoint:
`https://nestui.store/api/1.1/wf/`

### 🔐 Authentication
Secure your API requests with API key authentication. 
> **⚠️ CRITICAL:** NestUI requires the API key to be passed **directly inside the JSON payload (body)** of your requests. Do not use HTTP headers or query strings for authentication.

**Required Parameter (JSON Body):**
```json
{
  "api_key": "YOUR_API_KEY" 
}

1. Text-to-Image
Endpoint: POST /text_to_image
Status Check: POST /text_to_image_status_get
{
  "api_key": "YOUR_API_KEY",
  "prompt": "Cyberpunk city at night",
  "size": "1024x1024"
}

2. Text-to-Video
Endpoint: POST /text_to_video
Status Check: POST /text_to_video_status_get
{
  "api_key": "YOUR_API_KEY",
  "prompt": "A dragon flying over mountains",
  "size": "1920x1080",
  "duration": "10"
}

3. Image-to-Video
Endpoint: POST /image_to_video
Status Check: POST /image_to_video_status_get
{
  "api key": "YOUR_KEY",
  "image url": "https://example.com/start_frame.jpg",
  "audio url": "https://example.com/bg_music.mp3",
  "resolution": "1280x720",
  "duration": 5,
  "prompt": "The camera pans slowly across the landscape"
}

4. Image-to-animation
Generate new versions of an existing image.
Endpoint: POST /image_to_animation
Status Check: POST /image_to_animation_status_get
{
  "api key": "YOUR_KEY",
  "image url": "https://example.com/portrait.jpg",
  "video url": "https://example.com/motion_ref.mp4"
}

5. Character Swap
Maintain character consistency across different images.
Endpoint: POST /character_swap
Status Check: POST /character_swap_status_get
{
  "api_key": "YOUR_KEY",
  "image_url": "https://example.com/source.jpg",
  "video_url": "https://example.com/target_video.mp4"
}

6. Images to video
The model generates a smoothly transitioning video from a first frame image, a last frame image, and a text prompt.
Endpoint: POST /images_to_video
Status Check: POST /images_to_video_status_get
{
  "api key": "YOUR_KEY",
  "first image url": "https://example.com/start.jpg",
  "second image url": "https://example.com/end.jpg",
  "resolution": "1024x1024",
  "prompt": "A smooth morphing transition between the two characters"
}

7. Image Editor
General image editing model edits images using text prompts.
Endpoint: POST /image_editor
Status Check: POST /image_editor_status_get
{
  "api key": "YOUR_KEY",
  "image url": "https://example.com/original.png",
  "prompt": "Change the background to a neon cyberpunk city"
}

8. Text-to-Speech (Instant)
Converts text to natural speech.
Endpoint: POST /text_to_speech
Note: This tool does not require a status check. The audio URL is returned immediately in the initial POST response.
{
  "api key": "YOUR_KEY",
  "prompt": "Welcome to NestUI, the future of AI research.",
  "voice": "Cherry",
  "language": "English"
}

📥 Response Format
All "Status Check" calls return:
{
  "status": "SUCCEEDED",
  "output_url": "[https://nestui.store/media/result.mp4](https://nestui.store/media/result.mp4)",
  "task_id": "xxxx-xxxx"
}
