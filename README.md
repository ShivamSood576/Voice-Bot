🎙️ Real-Time Conversational AI Server with Pipecat
This project implements a real-time voice-based conversational AI system using Pipecat, integrating:

Deepgram STT for Speech-to-Text

OpenAI GPT (gpt-4o-mini) for text generation

Deepgram TTS (Aura Helios) for Text-to-Speech

Optional Cartesia TTS (commented)

It leverages Pipecat's pipeline architecture and WebSocket transport to enable seamless, real-time audio conversations.

📦 Features
Real-time WebRTC audio interaction via WebSocket

Deepgram-powered speech recognition and speech synthesis

OpenAI GPT-powered dynamic conversational logic

Graceful session timeout handling with automated call ending

Supports multiple TTS engines (Deepgram, Cartesia)

Audio streaming with Voice Activity Detection (VAD) via Silero

📂 Project Structure
main.py: Core server script (provided above)

requirements.txt: List of dependencies (not provided, see below)

/templates/index.html: Simple WebRTC frontend client (served separately)

🚀 Setup Instructions
1️⃣ Clone the Repository:
bash
Copy
Edit
git clone https://github.com/your-username/your-repo.git
cd your-repo
2️⃣ Install Dependencies:
Ensure Python 3.9+ is installed. Install dependencies using:

bash
Copy
Edit
pip install -r requirements.txt
Sample requirements.txt:

plaintext
Copy
Edit
pipecat
python-dotenv
loguru
asyncio
Adjust as needed depending on your Pipecat version.

3️⃣ Configure Environment:
Create a .env file in the project root:

bash
Copy
Edit
OPENAI_API_KEY=your_openai_api_key
DEEPGRAM_API_KEY=your_deepgram_api_key
Alternatively, directly modify API keys in main.py.

▶️ Running the Server
Start the server using:

bash
Copy
Edit
python main.py
Once running, the WebSocket server will handle incoming audio streams.

🌐 Serve HTML Client
To enable users to connect via a web browser, serve your HTML frontend. Example using SimpleHTTPServer:

bash
Copy
Edit
cd templates
python -m http.server 8000
Access the client at:

arduino
Copy
Edit
http://localhost:8000
💡 Important: The HTML client should establish a WebSocket connection to your running server. Refer to Pipecat WebRTC documentation for client setup.

⚙️ Customization
Modify TTS engine in main.py by switching between DeepgramTTSService and CartesiaTTSService.

Change the initial messages for custom assistant personality.

Adjust session timeout via:

python
Copy
Edit
session_timeout=60 * 3  # in seconds
📄 References
Pipecat Docs

Deepgram API

OpenAI GPT API
