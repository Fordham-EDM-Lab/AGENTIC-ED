# MAESTRO

**MAESTRO** (Multi-Agent Educational System for Training and Online Learning) is an AI-powered system designed to automate the creation of engaging educational video lectures.  Leveraging Large Language Models (LLMs) and Text-to-Speech (TTS) technologies, MAESTRO offers two distinct pipelines for generating video content:

*   **Image-to-Video:** Transforms existing slide decks (PDF presentations) into narrated video lectures, complete with instructor-style voiceover and synchronized visuals.
*   **Text-to-Video:** Generates animated educational videos from text-based lesson outlines, utilizing AI agents to create dynamic slides and accompanying narrations.

## Sample videos

### Sample videos

https://github.com/user-attachments/assets/73bbb39e-0f60-47fa-aa14-e267720b5f8d

https://github.com/user-attachments/assets/3ea7d03d-e211-4a1e-979e-90d03145c4fa

https://github.com/user-attachments/assets/2589be42-c4f7-4f26-a656-b97e6b58ce20

You can find and download these and the rest of the sample videos generated by MAESTRO to see the system in action in the `media` directory.

### `media` directory structure

The `media` directory comprises the following subdirectories with the corresponding files:

- media/Image-To-Video (`K-Means_TTS-1.mp4`, `KNN_TTS-1.mp4`)
- media/Text-To-Video (`K-Means_TTS-1.mp4`, `K-Means_Clone.mp4`, `KNN_TTS-1.mp4`, `KNN_Clone.mp4`)

## How to use source code

**Prerequisites:**

*   **Python 3.x**
*   **Required Python Packages:** (List them here - you can get this from your `requirements.txt` if you have one, or by listing key libraries like `openai`, `fitz`, `pptx`, `ffmpeg-python`, `Flask`, etc.)
    ```bash
    pip install -r requirements.txt
    ```

*   **OpenAI API Key:** You will need an OpenAI API key to use the LLM and TTS functionalities.

### To use Image-To-Video through terminal:

1.  **Navigate to the `src/Image-to-Video` directory:**
    ```bash
    cd src/Image-to-Video
    ```

2.  **Run the `video_generator.py` script:**

    ```bash
    python video_generator.py path/to/your/presentation.pdf your-openai-api-key --output output_video.mp4
    ```
    *   Replace `path/to/your/presentation.pdf` with the actual path to your PDF slide deck.
    *   Replace `your-openai-api-key` with your OpenAI API key.
    *   `--output output_video.mp4` specifies the desired output filename (optional, defaults to `slideshow.mp4`).

### To chat with the content (after generating Image-to-Video):

1.  **Navigate to the `src/Image-to-Video` directory:**
    ```bash
    cd src/Image-to-Video
    ```

2.  **Run the `chat.py` script:**

    ```bash
    python chat.py output/scripts your-openai-api-key
    ```
    *   `output/scripts` assumes you have already generated scripts using `video_generator.py` and they are located in the `output/scripts` directory (default behavior of `video_generator.py`). Adjust the path if necessary.
    *   Replace `your-openai-api-key` with your OpenAI API key.

    This will launch a simple command-line interface for chatting with the content of your generated lecture.
