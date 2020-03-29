### `SpeechSynthesis`

这是一个实验中的 API,不同浏览器提供的语音可能会不同

```javascript
function speak() {
        const synth = window.speechSynthesis;
        let voices = synth.getVoices().filter(voice => voice.lang.startsWith(document.querySelector('html').lang));
        if (voices.length == 0) return;
        let utterThis = new SpeechSynthesisUtterance(document.querySelector('.content').textContent);
        utterThis.voice = voices[0];
        synth.speak(utterThis);
    }
```
