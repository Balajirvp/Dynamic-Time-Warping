# Dynamic Time Warping

[![Version](https://img.shields.io/badge/version-1.0-orange.svg)]()
[![Python Version](https://img.shields.io/badge/python-v3.9.15+-blue.svg)]()
[![Last Commit](https://img.shields.io/github/last-commit/Balajirvp/Dynamic-Time-Warping.svg)](https://github.com/Balajirvp/Dynamic-Time-Warping/commits)
[![Documentation](https://img.shields.io/badge/documentation-yes-brightgreen)]()
[![Contributions](https://img.shields.io/badge/contributions-welcome-brightgreen)]()

Dynamic Time Warping (DTW) is a technique used to measure the similarity between two sequences of temporal events, accommodating variations in their speeds. In this project, I intend to utilize DTW to assess the similarity between specific audio tracks: "My Flame" by Bobby Caldwell, "Sky's the Limit" by The Notorious B.I.G. (which samples "My Flame"), and "Take Five" by Dave Brubeck.

- Song 1 - My Flame by Bobby Caldwell (https://www.youtube.com/watch?v=3hK6IgvZ0CY)
- Song 2 - Sky's the Limit by The Notorious B.I.G. (https://www.youtube.com/watch?v=d3vOeCkeCNA)
- Song 3 - Take Five by Dave Brubeck (https://www.youtube.com/watch?v=vmDDOFXSgAs)

It's noteworthy that Song 2 ("Sky's the Limit") is sampled from Song 1 ("My Flame"), while Song 3 ("Take Five") is entirely distinct from the first two songs.

For the purpose of this project, DTW will be applied solely to the instrumental versions of the songs. Due to computational considerations, the analysis will focus on the initial 30 seconds of each track. By employing DTW on these selected segments, I aim to compute similarity scores and quantify the degree of resemblance between the songs.

## 1) Converting the .mp4 files into .wav files

In this section, I extracted the audio content from the .mp4 video files (which I downloaded) and converted them into the widely used .wav audio format. This step is essential for further analysis and processing of the audio data. Each .mp4 file will be processed to produce a corresponding .wav file, focusing on the audio component for subsequent Dynamic Time Warping (DTW) analysis.

![image](https://github.com/Balajirvp/Dynamic-Time-Warping/assets/104417912/9d29989e-e782-4ab1-86e6-cf493a46a664)

![image](https://github.com/Balajirvp/Dynamic-Time-Warping/assets/104417912/3da080f3-99de-4402-8d22-935439004c3a)

## 2) Loading the .wav files and visualizing their audio frequencies

A Mel spectrogram, also known as a Mel-frequency spectrogram, is a representation of an audio signal's frequency content in a way that is more perceptually relevant to human hearing. It's a popular tool used in speech and audio processing tasks. I will be using the librosa package to visualize the 3 songs with the help of a log Mel-frequency spectrogram. The logarithm (log) transformation is applied to the Mel spectrogram because it helps replicate the logarithmic perception of loudness by the human auditory system. This makes the visualization more aligned with how we perceive audio, especially at different frequencies and amplitudes. It's a common practice in audio processing to use the log scale to better capture the human auditory experience and highlight the relevant features for analysis.

![image](https://github.com/Balajirvp/Dynamic-Time-Warping/assets/104417912/8c0f2799-7e0c-4359-8f5d-d2aa15de3e99)

![image](https://github.com/Balajirvp/Dynamic-Time-Warping/assets/104417912/39402db7-10af-4cc3-bff4-2f224b3cdb70)

![image](https://github.com/Balajirvp/Dynamic-Time-Warping/assets/104417912/8c7df5a2-2436-4a5e-b69e-aa7e42cf2ffd)

## 3) Performing DTW

With the assistance of Dynamic Time Warping (DTW), we can determine the alignment cost between the songs, providing insights into their level of similarity. DTW is particularly effective in comparing sequences with different speeds, making it well-suited for our task of comparing audio tracks.

To facilitate a more meaningful comparison, we will focus on the normalized alignment cost, a crucial metric derived from DTW. The normalized alignment cost is obtained by normalizing the alignment cost with respect to the lengths of the sequences being compared. It provides a standardized measure of similarity, enabling fair comparisons irrespective of sequence length.

In interpreting the results, a lower normalized alignment cost indicates a higher degree of similarity between the songs. Conversely, a higher normalized alignment cost signifies greater dissimilarity. This metric simplifies the assessment of similarity levels, aiding in the determination of how closely related the songs are in terms of their audio characteristics.

- Alignment between Song 1 and 2

![image](https://github.com/Balajirvp/Dynamic-Time-Warping/assets/104417912/60522b5d-e5d5-475d-b288-d244052d8e9a)

- Alignment between Song 1 and 3

![image](https://github.com/Balajirvp/Dynamic-Time-Warping/assets/104417912/9b70377c-a53d-4269-ab84-a9d5dc67ff88)

-  Alignment between Song 2 and 3

![image](https://github.com/Balajirvp/Dynamic-Time-Warping/assets/104417912/4733ef1f-ffae-45c4-9314-ef717e82d02c)

Upon reviewing the results, it's evident that the alignment cost between songs 1 and 2 is notably lower compared to the alignment cost between songs 1 and 3, as well as between songs 2 and 3. This disparity in alignment costs strongly indicates a higher degree of similarity between songs 1 and 2. This aligns with the expectation, considering that song 2 is sampled from song 1. These results from DTW affirm the inherent musical resemblance between these two tracks.
