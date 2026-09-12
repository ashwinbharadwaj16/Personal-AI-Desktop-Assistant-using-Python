# 🤖 Personal AI Desktop Assistant

A Python-based voice-enabled desktop assistant that combines **speech recognition, OpenAI API integration, text-to-speech, and local system automation** to provide an interactive hands-free experience.

The assistant can understand spoken commands, perform common desktop and web actions, and use an AI model to generate natural-language responses for general queries.

---

## ✨ Features

* 🎙️ **Voice Command Recognition**

  * Converts spoken commands into text using speech recognition.
  * Supports continuous interactive conversations.

* 🧠 **OpenAI API Integration**

  * Uses the OpenAI API to process general questions and generate natural-language responses.
  * Provides conversational interaction beyond predefined commands.

* 💻 **Desktop Automation**

  * Opens applications and performs supported local system actions.
  * Provides a simple interface for interacting with the desktop using voice commands.

* 🌐 **Web Automation**

  * Opens commonly used websites through voice commands.
  * Supports commands such as opening YouTube and other configured websites.

* 🎵 **Media Control**

  * Supports launching music and other configured media actions.

* 🕒 **Utility Commands**

  * Provides basic utilities such as checking the current time.

* 🔊 **Text-to-Speech**

  * Converts assistant responses into speech for a hands-free interaction.

* 📝 **Conversation / Prompt Logging**

  * Saves selected interactions or generated responses to local files for later reference.

---

## 🏗️ System Architecture

```text
                    ┌──────────────────┐
                    │    Microphone    │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │ Speech Recognition│
                    └────────┬─────────┘
                             │
                       Spoken Command
                             │
                             ▼
                    ┌──────────────────┐
                    │ Command Processor│
                    └────────┬─────────┘
                             │
                ┌────────────┴────────────┐
                │                         │
                ▼                         ▼
       ┌─────────────────┐       ┌─────────────────┐
       │ Local Commands  │       │   AI Commands   │
       ├─────────────────┤       ├─────────────────┤
       │ Open Websites   │       │ OpenAI API      │
       │ Launch Apps     │       │ General Queries │
       │ Music           │       │ AI Responses    │
       │ Time / Utility  │       │ Conversation    │
       └────────┬────────┘       └────────┬────────┘
                │                         │
                └────────────┬────────────┘
                             ▼
                    ┌──────────────────┐
                    │ Assistant Output │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │ Text-to-Speech   │
                    └──────────────────┘
```

---

## 🛠️ Technology Stack

| Technology                | Purpose                                      |
| ------------------------- | -------------------------------------------- |
| **Python**                | Core application development                 |
| **SpeechRecognition**     | Speech-to-text conversion                    |
| **OpenAI API**            | Natural-language processing and AI responses |
| **Text-to-Speech**        | Voice-based assistant responses              |
| **Web Browser / OS APIs** | Desktop and web automation                   |
| **File I/O**              | Local interaction and response logging       |

---

## 📂 Project Structure

```text
Personal-AI-Desktop-Assistant-using-Python/
│
├── main.py
├── config.py
├── openaitest.py
├── README.md
├── .gitignore
└── requirements.txt
```

### `main.py`

Contains the primary assistant workflow, including:

* Voice input
* Command processing
* Local automation
* Assistant responses
* Text-to-speech interaction

### `config.py`

Contains application configuration and environment-related settings.

### `openaitest.py`

Contains OpenAI API-related functionality and testing.

### `requirements.txt`

Contains the Python dependencies required to run the project.

---

## ⚙️ How It Works

The assistant follows a simple command-processing workflow.

### 1. Capture Voice Input

The application listens through the system microphone and captures the user's spoken command.

```text
User speaks
     ↓
Microphone
     ↓
Speech Recognition
     ↓
Text command
```

### 2. Process the Command

The recognized text is passed to the command-processing logic.

Commands that match supported local actions are handled directly.

For example:

```text
"Open YouTube"
        ↓
Local command handler
        ↓
Web browser
        ↓
YouTube
```

### 3. Handle AI Queries

For general questions or commands that require natural-language processing, the application sends the request to the OpenAI API.

```text
User Query
    ↓
Command Processor
    ↓
OpenAI API
    ↓
Generated Response
```

### 4. Provide Voice Feedback

The generated or predefined response is converted into speech using the configured text-to-speech functionality.

```text
Response
    ↓
Text-to-Speech
    ↓
Speaker
```

---

## 🚀 Getting Started

### Prerequisites

Make sure the following are installed:

* Python 3.x
* Git
* Working microphone
* Internet connection
* OpenAI API access

You can verify your Python installation using:

```bash
python --version
```

---

## 📥 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/ashwinbharadwaj16/Personal-AI-Desktop-Assistant-using-Python.git
```

Navigate to the project directory:

```bash
cd Personal-AI-Desktop-Assistant-using-Python
```

### 2. Create a Virtual Environment

```bash
python -m venv venv
```

Activate the virtual environment.

#### Windows

```bash
venv\Scripts\activate
```

#### Linux / macOS

```bash
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 🔐 API Configuration

The assistant uses the OpenAI API for AI-generated responses.

Create an environment variable containing your API key rather than hard-coding credentials into the source code.

### Windows

```bash
set OPENAI_API_KEY=your_api_key
```

### Linux / macOS

```bash
export OPENAI_API_KEY=your_api_key
```

> **Security Note:** Never commit an API key, password, access token, or other secret directly to GitHub.

If configuration is handled through `config.py`, make sure sensitive values are excluded from version control.

---

## ▶️ Running the Application

After installing the dependencies and configuring the required environment variables:

```bash
python main.py
```

The assistant will start listening for supported voice commands.

---

## 💬 Example Commands

Some example interactions include:

```text
"Open YouTube"
```

```text
"What is the current time?"
```

```text
"Play music"
```

```text
"Open [configured application]"
```

For general questions:

```text
"Explain what an API is"
```

The command is processed through the OpenAI API and the generated response is returned through the assistant.

---

## 🔄 Command Processing Flow

```text
                    User
                     │
                     ▼
              Voice Command
                     │
                     ▼
             Speech-to-Text
                     │
                     ▼
             Command Processor
                     │
          ┌──────────┴──────────┐
          │                     │
          ▼                     ▼
   Known Local Command     General Query
          │                     │
          ▼                     ▼
   Local System Action      OpenAI API
          │                     │
          │                     ▼
          │              AI-generated response
          │                     │
          └──────────┬──────────┘
                     ▼
               Final Response
                     │
                     ▼
               Text-to-Speech
                     │
                     ▼
                  User
```

---

## 🧩 Key Design Concepts

### Command Routing

The assistant distinguishes between supported local commands and general-purpose questions.

This allows frequently used actions to be handled locally while delegating open-ended queries to the AI service.

### API Integration

The project demonstrates integration with an external AI API from a Python application, including sending user input and handling the generated response.

### Voice-Based Interaction

Speech recognition and text-to-speech provide a hands-free interface instead of requiring every interaction to be typed.

### Local Automation

The assistant can interact with supported applications and websites through Python-based system and browser functionality.

---

## 🧪 Testing

The application can be tested using different categories of commands:

### Voice Recognition

* Clear voice commands
* Different command lengths
* Commands with background noise

### Local Commands

* Opening websites
* Launching configured applications
* Utility commands
* Media-related commands

### AI Queries

* General questions
* Technical questions
* Natural-language requests

### Error Handling

The application should gracefully handle cases such as:

* Unrecognized speech
* Empty input
* Network failures
* API failures
* Unsupported commands

---

## 🔒 Security Considerations

The project uses an external API and therefore requires appropriate handling of credentials.

Recommended practices:

* Store API credentials outside source code.
* Use environment variables for secrets.
* Do not commit `.env` files containing credentials.
* Add sensitive configuration files to `.gitignore`.
* Rotate an API key immediately if it is accidentally exposed.

Example `.gitignore` entries:

```gitignore
.env
venv/
__pycache__/
*.pyc
```

---

## ⚠️ Limitations

This project is designed as a personal desktop assistant and has several limitations:

* Speech recognition accuracy depends on microphone quality and network conditions.
* Some commands are limited to predefined functionality.
* OpenAI API functionality requires internet access and a valid API configuration.
* Desktop automation can be platform-dependent.
* The assistant does not provide unrestricted control over the operating system.

---

## 🔮 Future Improvements

Potential improvements include:

* [ ] Improved natural-language command routing
* [ ] More desktop automation capabilities
* [ ] Better handling of speech-recognition errors
* [ ] Conversation history management
* [ ] Configurable voice commands
* [ ] More robust exception handling
* [ ] Support for additional operating systems
* [ ] Improved logging and debugging
* [ ] Modular command-handler architecture
* [ ] Unit tests for command processing
* [ ] Improved configuration management

---

## 🎯 Learning Outcomes

This project provided practical experience with:

* Python application development
* Speech recognition
* Text-to-speech systems
* REST/API integration
* OpenAI API usage
* Desktop automation
* File handling
* Environment-based configuration
* Exception handling
* Building an interactive application around an external AI service

---

## 👨‍💻 Author

**Ashwin Bharadwaj**

GitHub:
https://github.com/ashwinbharadwaj16

---

## 📄 License

This project is intended for educational and personal portfolio purposes.
