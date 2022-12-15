# Project Proposal - _Lucky Lizard_
## Team Members
1. Andi Nur Asyikin Binti Andi Zainuddin
2. Lim Yong Chuan
3. Nur Fatini Binti Isa

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
1. STM32  Nucleo-64 (stm32f411) <br> ![2](https://user-images.githubusercontent.com/118822144/207986513-efabb533-804c-4230-8470-33c5c2a8424c.JPG) <br>
2. Jumper Wire <br> ![3](https://user-images.githubusercontent.com/118822144/207986515-1716a85c-5ed7-45ca-9740-227f89b61d82.JPG) <br> ![4](https://user-images.githubusercontent.com/118822144/207986517-0db0762f-ace7-471d-8b78-1afe4f3fd89b.JPG) <br>
3. RED LED <br> ![5](https://user-images.githubusercontent.com/118822144/207986522-97506541-c393-45f3-bc07-b099aa322fd9.JPG) <br>
4. Buzzer <br> ![6](https://user-images.githubusercontent.com/118822144/207986523-b2f7580e-6564-482a-9436-08a2c94c58d0.JPG) <br?
5. Breadbroad <br> ![7](https://user-images.githubusercontent.com/118822144/207986503-aebba739-7513-444c-b061-6d325abe89dc.JPG) <br> <br>
6. Microphones <br> ![8](https://user-images.githubusercontent.com/118822144/207986508-a054d44a-9d1c-4292-bcbb-28bd57b33dd2.JPG) <br?


### Hardware Draft Design
The general idea of the hardware design is shown below. <br>
![9](https://user-images.githubusercontent.com/118822144/207986511-02f55b67-2d15-4207-b3ca-e095c90d32cb.JPG)
From Figure 9 above, at input it has a microphone that translates sound vibrations in the air into electronic signals and scribes them to a recording medium or over a loudspeaker. This microphone will act as input signal for the speech/keyword that detected. Then, the data then will be analyze using the microprosscor, which is in this case using the STM32F411. Then when a certain keyword is detected, and successfully processed by the data, the STM32 will sent a output signal to the buzzzer and to the LED. At the ouput, when the signal received, the buzzer will ring while the LED will light on and off which indicates the morse code " S-O-S" which is a signal to indicates danger situations.

### Software Tools
The software algorithm of this project is as shown figure 10 below. <br>
![10](https://user-images.githubusercontent.com/118822144/207986512-cb7bec78-d9cb-4b1b-86a8-656fce609460.JPG) <br><br>
1. ***STM32CubeIDE*** <br>
The project will be setup in the STM32CubeIDE. All the pin configurations of the peripherals to the board will be defined in this software. The code generated will then be modified, compiled and executed in the same software. <br>
Since this project will mainly be on keyword spotting of the audio input, the I2S protocol of STM32CubeIDE will be incorporated into the project design. I2S (IC-to-IC sound) is an audio data transfer standard that uses a three-line bus for serial and synchronous data delivery. The I2S protocol will be set up for the input peripheral, which is the microphone to help in receiving audio inputs in the form of pulse-code modulation (PCM) and send them to the target.<br>
2. ***Edge Impulse***
As for achieving the desired model of the keyword spotting system, an open-source tool called Edge Impulse will be used to train the model. Edge Impulse is currently the most popular development platform for STM32 embedded machine learning. Machine Learning at the edge will make use of the 99% of sensor data that is currently wasted due to cost, bandwidth, or power limits. The raw audio data will be initialized and compared with the dataset available for that specific word. Once the machine has been trained, the code in STM32CubeIDE will be modified to get desirable inputs. 

# Conclusion
In short, the proposed project is a keyword-spotting system using Nucleo-F443RE. The proposed methodology is applying MFCC audio signal processing techniques and fed into a Neural network. When keyword A is detected, a morse code will be transmitted by LED as a sign of seeking help subtlety while when keyword B detected, a buzzer will be turned ON as an extreme emergency indicator. 

# Reference
[1]     	M. N. Miah and G. Wang, “Keyword Spotting with Deep Neural Network on Edge Devices,” in 2022 IEEE 12th International Conference on Electronics Information and Emergency Communication (ICEIEC), Jul. 2022, pp. 98–102. doi: 10.1109/ICEIEC54567.2022.9835061.<br>
[2]     	J. Lei et al., “Low-power audio keyword spotting using tsetlin machines,” Journal of Low Power Electronics and Applications, vol. 11, no. 2, Jun. 2021, doi: 10.3390/jlpea11020018. <br>
[3]     	S. Yin et al., “A 141 UW, 2.46 PJ/Neuron Binarized Convolutional Neural Network Based Self-Learning Speech Recognition Processor in 28NM CMOS,” in 2018 IEEE Symposium on VLSI Circuits, Jun. 2018, pp. 139–140. doi: 10.1109/VLSIC.2018.8502309. <br>
[4]     	R. Shafik, A. Yakovlev, and S. Das, “Real-Power Computing,” IEEE Transactions on Computers, vol. 67, no. 10, pp. 1445–1461, Oct. 2018, doi: 10.1109/TC.2018.2822697. <br>
[5]     	B. Liu et al., “An Ultra-Low Power Always-On Keyword Spotting Accelerator Using Quantized Convolutional Neural Network and Voltage-Domain Analog Switching Network-Based Approximate Computing,” IEEE Access, vol. 7, pp. 186456–186469, 2019, doi: 10.1109/ACCESS.2019.2960948. <br>
[6]     	G. Chen, C. Parada, and G. Heigold, “Small-footprint keyword spotting using deep neural networks,” in 2014 IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP), May 2014, pp. 4087–4091. doi: 10.1109/ICASSP.2014.6854370. <br>



