This is a somewhat modified sample code from [session 509 WWDC 2016](https://developer.apple.com/videos/play/wwdc2016/509) on speech recognition

![](https://raw.github.com/zats/SpeechRecognition/master/website/screen.gif)

The goal of this demo is to generate real time subtitles by recognizing the audio feed from the video while playing it back.

## Important notes

1. While I used [this video from Realm Live](https://realm.wistia.com/medias/u3xprtodqi) as a sample, all copyrights belong to their respective owners. It was the video I saw on Twitter when I came up with this idea, plus it has a clear audio track (kudos to Chris) which makes it easier to recognize speech. Also sorry for the video asset, it is quite big - 23Mb.

2. Recognition is happening locally on device **every time** you are playing video, so it might be good if you are broadcasting a live interview, but probably not such a great idea if you are Netflix and can generate subtitles videos before publishing.

3. Many thanks to engineers from AVFoundation, CoreAudio, SiriKit and SpeechRecognition teams for helping to figure out details of this demo, without them this demo would not exist! 💖

4. `SFSpeechRecognizer` doesn't seem to be designed with this usecase in mind, it is intended more for short interactions with your app such as a voice command or a search query dictation. It stops recognizing input over a certain duration (currently around 1 minute). In this sample I am simply re-creating recognition request every time it finishes.

5. While most of the times recognition works fairly well, I noticed that sometimes it would lag behind the video or even gets stuck - might be quirks of the first iOS 10 beta seed or something that I messed up with implementation (while sometimes it just works™). 

6. To conclude, while it is an amazing technology, it seems like Apple sees it as a more appropriate tool for short voice input or transcribing voice messages (like those in Whatsapp or Voice Mail app). Also I can definitely see it improving accessibility in apps like Vine (but then again, certain things are better to be done once on the server).