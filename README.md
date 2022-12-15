# Project Proposal - _Lucky Lizard_

## Title : Keyword Spotting as a Spy Protection Alarm


# Abstract
Keyword Spotting is a speech processing where it deals with the identification of keywords in utterances. It is widely applied in phone calls or audio recordings. Nowadays, most technology relies on automation, whether it is for data processing, decision-making, or home automation. Convolutional Neural Network (CNN), which is currently in use, is one of the examples. With voice recognition, CNN frequently reads audio as input, interprets it, and then takes the appropriate action based on the input.  Most home automation systems, including those from Amazon's Echo line, Google Home, and Apple's HomeKit, had their own methods for processing speech recognition and required a network connection in order to access the cloud's database.  Another application of this CNN is processing a keyword where it detects the situation is in danger once it has completed processing a certain unit to the device. Thus, it will apply in home/building automation systems as a safety or protection alarm for humans. Therefore,  the  aim  is  to  make  simple home automation locally which detect a certain keyword to detect any crime/danger and produce an output through the external hardware. This project aim only connected it locally without connecting to the network.Keywords—Convolutional   Neural   Network   (CNN); RSIC; Memory interface;

# Introduction
Keyword spotting systems work by enabling a hands-free speech recognition experience through the detection of a trigger phrase that is used to initiate interaction with a device. The inventor can decide which utterances or words will serve as triggers and what to do when they are recognised. This keyword spotting models only search for a few selected words, and this makes it less energy consuming to the device. This can be seen in Apple device where they user can call “Hey Siri !” to wake up the device in a standby mode waiting for the user for the next instruction for speech recognitions.<br><br>
  In addition to being widely utilised in home automation, keyword spotting also converts audio files into text using speech recognition and NN. After that, it examines user speech characteristics like frequency and pitch to provide feature values. Moreover, keyword spotting also can be implement in building system such as parking era to detect a certain keyword and the output will triggered a certain hardware installed such as light or alarm. <br><br>
  For this project the  aim  is  to  make  simple building  automation  locally  without connecting   to   the   network. Full   large-vocabulary   speech recognition   is unnecessary  and   too   complex   for  practical applications.  This  application  just  needs  to  recognize  simple words such as “help help”. Thus, keyword spotting which   refers   to   small-vocabulary   speech   recognition   is sufficient for this project. <br><br>

# Literature Review 
Interconnected devices are gaining popularity as a means of integrating physical information and making them more accessible for further research. The growing number of sensors necessitates massive bandwidth and processing capacity on the cloud. Furthermore, the constant transfer of data to a distant server would jeopardize privacy. Deep Neural Network (DNN) is proving to be extremely successful for cognitive tasks and is simple to install on edge devices[1], [2]. <br><br> 
For fine-tuning feature weights, the NN-based models use arithmetic-intensive gradient descent calculations. To balance the contradiction between performance and accuracy, the weights must be adjusted using a large number of system-wide parameters known as hyperparameters[3]. Given that these components, as well as their complicated controls, are inherent in the NN paradigm, energy efficiency has remained a challenge[2], [4]. <br><br>
The earliest keyword spotting(KWS) classification algorithms introduced in the late 1970s relied on MFCCs for feature extraction since the coefficients generated had a relatively low dimensionality when compared to the raw input data at the time [2]. It was further shown that, when compared to other audio extraction approaches like close prediction coding coefficients (LPCCs) and perceptual linear production (PLP), MFCCs perform much better with increasing background noise and low SNR [2], [5]. <br><br>
Later it was proven that Recurrent Neural Networks (RNNs) outperform HMMs but suffer from operational delay as the issue grows, yet RNNs still have quicker run-times than HMM pipelines as they do not need a decoder method. Deep Neural Networks (DNN) was utilized to minimise latency since they consume less memory and operate faster than HMMs[6]. Common DNN optimization strategies like pruning, encoding, and quantization contribute to accuracy decreases in KWS applications[2], [5]. <br><br>

# Methodology
### Testing Methodolody
![1](https://user-images.githubusercontent.com/118822144/207984389-7eb4489c-dab0-48be-bbcd-6fab4f745978.JPG) <br>
_Figure 1: Methodology for implementation_ <br>
Figure 1 shows the methodology to implement the keyword spotting system. Firstly, the audio data is collected through open source resources such as Google speech command dataset, or a manually-created process. The collected data is processed with Mel-frequency cepstral coefficients (MFCC) which is an audio processing technique. This is due to raw audio data that may contain noise that can corrupt the original signal. MFCC involves a sequence of signal-processing operations to extract the features of audio files. When the audio files are processed, it is split into the training dataset and the test dataset. The training dataset will be fed into the neural network and the accuracy is determined by using the test dataset. Edge impulse provides both audio processing features and neural networks. Once the neural network is trained successfully, the model will be exported into the STM32 microprocessor for further operation. 

The microphone will be connected to the system and keep reading audio signals to spot the keyword. There are 2 keywords which are A and B. When the A is spotted, a series of morse codes “S-O-S” will be transmitted by LED. This shows that a person is in danger and is subtly requesting help. On the other hand, when B is spotted, this indicates that a person is in extreme danger and requests immediate help. A buzzer will be turned ON to alert the occurrence of this situation. 

### Hardware Design
A few components of electronic hardware needed for this project. It is shown as below <br>
***List of Equipment/Electronic Components :-*** <br>
1. STM32  Nucleo-64 (stm32f411)
2. Jumper Wire
3. RED LED
4. Buzzer
5. Breadbroad
6. Microphones
