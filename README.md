# Llama2Robot-GGML
Status: Beta. 
* Currently updates will be something along the lines of:
Implementation of text to speech through Native Windows TTS, this will be a feature for windows users only, so if the scripts are not run on wse, such as linux, then they should be automatically disabled. os dependent built in, windows wsl and linux, compatible text to speach, or if required then libraries too. The speech feature are intended to read updates to "session_history" key in, as possible, then a robotic voice. There should be an option of --nospeach to additionally turn the relevant code off for both, windows and linux, but there should be a place holder for linux TTS, that are able to be developed by other users of the framework I am creating....currently details for instructions on TTS, are irrellevant, as I am updating README.md as I go, but no update yet for that.
  
### DESCRIPTION:
* This is a Llama 2 language model and llama-cpp based chatbot/agent framework. It uses Python scripts, YAML files, and ASCII art to produce context-aware conversations. The framework is designed for the creation of future Llama 2 based projects through forks. Llama2Robot a your own project, can be further developed for, reading and modifying and redacting, files and content, supposedly with multi-line output, furthermore, the second window can be easily, replicated and modified, to add additonal windows for displaying other keys of your choice.  

### FUTURE PLANS:
1) Application Sounds for major events, with an optional --nosounds, to disable sounds at commandline.
2) implement a --speech switch, to enable built-in os dependent text to speech code.
3) Update to GGUF based models, and try to keep support for GGML in process. Tried 4 times to create script, with, ctransformers, transformers and llama.cpp, none worked due to lack of available concise information.
4) Figure out some system of prompt format for model, maybe even integrate short prompt test and selection useing code from "llama2syntax", something alike select which syntax worked best.

### FEATURES:
* `.ENV` File Management: Creates a default `.ENV` file if it doesn't exist. Useful for later forks.
* Multi-Window Interface: Runs separate scripts in parallel, bypassing the complexities of curses or tkinter on WSL.
* Context Support: Supports 4K-200K context multi-models with a robust interface for chat or chat+instruct models.
* Dynamic Model Initialization: Optimizes thread settings for the Llama language model.
* Interactive User Loop: Features a continuous loop for real-time user interaction.
* Intelligent Response Generation: Utilizes predefined prompts and ASCII art to generate contextually relevant and coherent responses.
* Model Response Rotation: Enhances character dialogue and can be modified for loop avoidance.
* YAML State Management: Manages session state, user preferences, and more through YAML file operations.
* User-Friendly Chat Interface: Offers a clean and intuitive chat interface, complete with ASCII art and dialogue history.
* Customizable Model Selection: Allows users to select from a list of available Llama 2 GGML models in the `./models` directory.


### INTERFACE:
Images may be from differing versions...
* Window 1 - Starting up, this also involves Wise-Llama's choice of fortune cookie!...
```
==========================================================================================
     .____    .__                        ________ __________     ___.           __
     |    |   |  | _____    _____ _____  \_____  \\______   \____\_ |__   _____/  |_
     |    |   |  | \__  \  /     \\__  \ /  _____/|       __/  _ \| __ \ /  _ \   __\
     |    |___|  |__/ __ \|  Y Y  \/ __ \|       \|    |   (  <_> ) \_\ (  <_> )  |
     |_______ \____(____  /__|_|  (____  Y_______ |____|___ \____/|_____/\____/|__|
             \/         \/      \/     \/        \/        \/           \/
                                Welcome To Llama2Robot!
==========================================================================================
=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-

   \/
   l'> -=< "I used to be indecisive. Now I'm not so sure! It's a work in progress."
   ll
   ll
   LlamaSay~
   ||    ||
   ''    ''

=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-
=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-
 Initial Startup Processes:
------------------------------------------------------------------------------------------

 Optimizing for x86_64-T24...
 ...using 20 out of 24 threads.

 Clearing input.log...
 ...input.log cleared.

 Clearing output.log...
 ...output.log cleared.

 Emptying keys...
 ...Keys reset.

 Loading... [==============================================================] Complete.
```
* Window 1 - Robust multi-model support for Llama 2 GGML llms...
```
==========================================================================================
                                       MODEL SELECTION
==========================================================================================
=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-
 Model Setup Processes:
------------------------------------------------------------------------------------------

 Search For Models...
 Chat model is llama2_7b_chat_uncensored.ggmlv3.q2_K.bin - CTX 4k
 Instruct model is llama-2-7b-32k-instruct.ggmlv3.q2_K.bin - CTX 32k

 Loading chat model with context length 4096, be patient...
llama.cpp: loading model from ./models/llama2_7b_chat_uncensored.ggmlv3.q2_K.bin
llama_model_load_internal: format     = ggjt v3 (latest)
llama_model_load_internal: n_ctx      = 4096
llama_model_load_internal: ftype      = 10 (mostly Q2_K)
llama_model_load_internal: model size = 7B
llama_model_load_internal: mem required  = 4525.64 MB (+ 1026.00 MB per state)

 Loading instruct model with context length 4096, be patient...
llama.cpp: loading model from ./models/llama-2-7b-32k-instruct.ggmlv3.q2_K.bin
llama_model_load_internal: format     = ggjt v3 (latest)
llama_model_load_internal: n_ctx      = 4096
llama_model_load_internal: ftype      = 10 (mostly Q2_K)
llama_model_load_internal: model size = 7B
llama_model_load_internal: mem required  = 4525.64 MB (+ 1026.00 MB per state)

 Loading... [==============================================================] Complete.
```
* Window 2 - The ROLEPLAY SUMMARY, values of the relevant keys in a display...
```
==========================================================================================
                                     ROLEPLAY SUMMARY
==========================================================================================
=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-
 Human's Input:
------------------------------------------------------------------------------------------

 hello there! i am glad to meet you here in the middle of nowhere. do you come here often?!

=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-
=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-
 Wise-Llama's Response:
------------------------------------------------------------------------------------------

 "Hello, I'm Wise-Llama and this is my first time being here."

=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-
=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-
 Wise-Llama's State:
------------------------------------------------------------------------------------------

 indifferent

=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-
=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-
 Event History:
------------------------------------------------------------------------------------------

 Human greeted Wise-Llama with the words "hello there! i am glad to meet you here in the middle of nowhere" before inquiring about how often he comes to this location. Wise-Llama responded by introducing himself and sharing that it was his first time visiting the place, using the phrase "I'm Wise-Llama and this is my first time being here."

=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-
```

### USAGE:
* For Windows WSL:
1) **Download the Package**: Download the package and extract it to a dedicated folder. Open the folder in Windows Explorer with Admin rights or a shell with Admin privileges.
2) **Install Requirements**: Double-click `Install Requirements.bat` or run `wsl pip install -r requirements.txt` in the shell.
3) **Install Packages**: Double-click `Install Packages.bat` or run `wsl sudo apt-get install alsa-utils espeak` in the shell.
4) **Download Models**: Download the required GGML `*.bin` chat model files and place them in the `./models` folder. Note that the required `config.json` is already present in the `./models` folder.
5) **Launch the Application**: Double-click `Launch Llama2Robot.bat` to start the program.
6) **Optional - Window Resizing**: Hold down Ctrl and scroll your mouse wheel to resize the window to your liking.
7) **Optional Arguments**: Edit `Launch Llama2Robot.bat` to include or run Python with relevant arguments like `--output` to log raw input/output to `./data/*put.log`.
* For Linux (Untested):
1) **Download the Package**: Download the package and extract it to a dedicated folder. Open the folder in a shell with Admin privileges.
2) **Install Requirements**: Run `pip install -r requirements.txt` in the shell.
3) **Install Packages**: run `sudo apt-get install alsa-utils espeak`
4) **Download Models**: Download the required GGML `*.bin` chat model files and place them in the `./models` folder. Note that the required `config.json` is already present in the `./models` folder.
5) **Prepare Environment File**: Manually duplicate `./data/example.ENV` to `./.ENV`.
6) **Launch the Application**: Run `python main1.py` and `python main2.py` in separate shell windows to start the program.
7) **Optional - Window Resizing**: Resize the terminal window to your liking, ensuring to use at least 90 columns.
8) **Optional Arguments**: Run Python with relevant arguments like `--output` to log raw input/output to `./data/*put.log`.

*** EDIT
sudo apt-get install --fix-missing mpg321

### TEST PROMPTS:
* Designed for the default roleplay settings...
1) Hello there! I never thought I would see you here on the mountain, do you come here often?!
2) Wow, you can actually talk? That's super amazing! What brings you to this remote place?
3) You look very wise, are you knowledgeable, do you, know wise things and have wise thoughts?

### REQUIREMENTS:
* Windows with WSL or Linux (untested). Due to dependencies like jaxlib and jax[cpu] or jax[gpu] for Nvidia, WSL is recommended.
* Python 3.x and the packages listed in `requirements.txt`.
* Compatible with Llama 2 7b Chat 8Bit GGML models, such as [this one](https://huggingface.co/TheBloke/llama2_7b_chat_uncensored-GGML).

### DISCLAIMER:
* This program is in no way affiliated with the Llama 2 developers, it merely is a Chatbot that runs through the use of Llama 2 GGML based. models. The Llama 2 model has been chosen because it is the only local language model that has been reviewed on YouTube to my knowing at the time of, inception and creation, that are able to correctly write a ".json" file. Thus if this were the case with other models beforehand, it would be named after them. 
