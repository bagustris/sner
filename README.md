# sner
SNER = Speech Naturalness and Emotion Recognition. SNER is a very simple inference of speech emotion and naturalness using machine learning pre-trained model. The program focuses on light size and fast inference time. The model is saved in .joblib format (60MB) with inference time in less than one second (0.8s inference time for 13s audio file).    

## Input-output format 
Input: speech file (wav) readable by `audiofile` package   
Output: Score of valence, arousal, dominance, and naturalness in the range [-1, 1].  


## Installation
install dependencies

    python3 -m pip install -r requirements.txt
    
    
## Usage
    python3 predict_vadn.py -i input.wav
    
or (need to: chmod +x `predict_vadn.py`)

    ./predict_vadn.py -i input.wav
   
## Arguments

```
-i input file
-m path of pre-trained model i .joblib format
-s split, `chunks` (every duration seconds) or `full` (without split)
-d duration (in seconds) if split is chunks, default duration=10  
```

## Example
```
bagus@m049:sner_os_full$ ./predict_vadn.py -i bagus-test_16000.wav 
Valence, arousal, dominance, naturalness #0: [[-0.09434319  0.44684726 -0.08786711  0.09021541]]
Valence, arousal, dominance, naturalness #1: [[-0.14146665  0.6224453  -0.19895521  0.13970129]]
Valence, arousal, dominance, naturalness #2: [[-0.06549488  0.42078984 -0.07323465  0.14856477]]
Valence, arousal, dominance, naturalness #3: [[-0.09165932  0.6154841  -0.1972353   0.2185024 ]]
Valence, arousal, dominance, naturalness #4: [[-0.07417645  0.41887206 -0.05865883  0.22063532]]
Valence, arousal, dominance, naturalness #5: [[-0.04649594  0.53053147 -0.11787422  0.19543049]]
Valence, arousal, dominance, naturalness #6: [[-0.12129027  0.48048788 -0.11438508  0.14086896]]
Valence, arousal, dominance, naturalness #7: [[-0.07501961  0.50562567 -0.12277649  0.08429483]]
Valence, arousal, dominance, naturalness #8: [[-0.1845332   0.47495478 -0.1136996   0.09605219]]
bagus@m049:sner_os_full$ ./predict_vadn.py -i bagus-test_16000.wav -s full
Valence, arousal, dominance, naturalness: [[-0.1591546   0.37833244 -0.06329431  0.39182937]]
```

### Demo
YouTube:  https://youtu.be/doZbrVsPpSU  

[![asciicast](https://asciinema.org/a/472390.svg)](https://asciinema.org/a/472390)


### Citation

```
Bagus Tris Atmaja, Akira Sasou, and Masato Akagi, "Concurrent Speech Emotion and Naturalness 
Recognitions Using Multitask Learning", 2022.
```

### License and Contact
The software is provided as it is without any warranty. It is free for academic
and research purposes but prohibited for commercial. For commercial and other
questions, contact me at b-atmaja@aist.go.jp 