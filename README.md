# StT-ESP-IoT 
Converting Speech to Text and The Steps tp run ESP32
## Speech to Text Interface
![Screenshot 2022-07-21 080619](https://user-images.githubusercontent.com/108990560/180135538-bc549344-5d84-4b09-b878-67f2e5e54bc2.png)
## Java Script
In the code below, I invoked the Web Speech Recognition API and initialized an instance stored in  recognition variable.
After this, I made references to  #textbox and #instructions components I characterized in the HTML utilizing JQuery to control them from the code.
content variable keeps track of text the application has converted and displayed in the textarea from the HTML file.
recognition.lang='ar'; for arabic language.

ex Git :
```
var speechRecognition = window.webkitSpeechRecognition
var recognition = new speechRecognition()
var textbox = $("#textbox")
var instructions = $("#instructions")
var content = ''
recognition.continuous = true
recognition.lang ='ar';
recognition.onstart = function() {
 instructions.text("ابدأ التحدث")
}
```
The onstart event handler is triggered when the recognition API starts and has microphone access.

ex Git :
```
recognition.onstart = function() {
 instructions.text("ابدأ التحدث")
}
```
onresult event handler is triggered when the recognition API has successfully converted speech from the user’s microphone to text, and the data is made available via the event.results variable.

ex Git :
```
recognition.onresult = function(event) {
 var current = event.resultIndex;
 var transcript = event.results[current][0].transcript
 content += transcript
 textbox.val(content)
}
```
Now If click the اضغط للبدء button your speech will convert to text

### ESP Steps
