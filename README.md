# text-to-speech-streamlit
This Streamlit app allows you to convert text to audio files using the [Google Cloud Text-to-Speech API](https://cloud.google.com/text-to-speech/ "Google Cloud Text-to-Speech API")

App preview:
![Screenshot1](/static/img/tts_01.png?raw=true "Screenshot1")

## Features
Access to most of the Google TTS API features, including
- voice and language selection (including WaveNet voices)
- text and ssml support
- voice tuning (pitch, speaking rate)
- two output audio formats (LINEAR16 [.wav], MP3 [.mp3])
- audio profiles

You can play the audio from the converted text directly in the browser or download the audio file to your local machine.

## Requirements
Before you can begin, you must have a Google Cloud account and enable the Text-to-Speech API in the Google Cloud Platform Console.
Follow the steps on the official website:
https://cloud.google.com/text-to-speech/docs/before-you-begin

In a nutshell:
- Enable Text-to-Speech on a project.
  - Make sure billing is enabled for Text-to-Speech.
  - Make sure your project has at least one service account.
  - Download a service account credential key in the JSON format.
- Place the credentials key JSON file in this project's ***static*** folder and make sure to name the file ***credentials.json***

## Installation
Clone this repository
```bash
git clone https://github.com/awetomate/text-to-speech-streamlit.git
```
Install the Python requirements using the requirements.txt file. This will install Streamlit, the Google Cloud TTS Python package, and other dependencies.
```bash
pip install -r requirements.txt
```
Place the ***credentials.json*** file into the ***static*** folder. See the Requirements chapter above.

## Run the Streamlit app
```bash
streamlit run app.py
```
This command will start the streamlit app, will automatically open a browser window, and navigate to http://localhost:8501/

## How-to use the app
1. Choose between plain text and ssml as the input method using the radio buttons.
2. Enter your plain text or SSML markup into the text box.
3. Select and tune your voice
3.1. First, choose a language from the first dropdown menu. Both the ***Voice type*** and ***Voice*** dropdown menus will update automatically with the available selections.
3.2 Second, choose whether you want a Standard or WaveNet (if available in the selected language) voice using the ***Voice type*** dropdown.
3.3 Third, choose from the list of available voices in the ***Voice*** dropdown.
4. Choose between ***WAV*** (lossless) and ***MP3*** (lossy) as the output file type. 

Optionally: 
- Choose from one of the available profiles in the ***Audio Device Profile*** dropdown to optimize the audio experience for specific use cases.
- Change the ***Speed*** and ***Pitch*** to further customize the voice. 

5. Once you've entered some text, the ***Convert*** button appears. Press the button to start the text-to-speech conversion.
6. A ***Download*** button and a media player will appear on screen once the conversion has finished.
6.1 Play the message directly in your browser using the media player.
6.2 Download the audio file to your local machine using the ***Download*** button.

App preview:
![Screenshot2](/static/img/tts_02.png?raw=true "Screenshot2")