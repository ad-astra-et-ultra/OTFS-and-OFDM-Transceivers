# OTFS-and-OFDM-Transceivers
### Implementation of OFDM and OTFS transceivers on GNU Radio  (software defined radio or SDR)

### NOTE : The grc and python files are to be opened by using GNU Radio. [Download Here](https://www.gnuradio.org/)

#### OFDM TRANSCEIVER:

<h4> 
OFDM is a specialised FDM having the constraint that the sub-streams in which the main signal is divided, are orthogonal to each other. Orthogonal signals are signals that are perpendicular to each other. A main property of orthogonal signals is that they do not interfere with each other.
</h4>

 ![image](https://user-images.githubusercontent.com/92263062/187748871-a809cc42-c333-4666-ac7e-550f3857427c.png)
 
<h4>
When any signal is modulated by the sender, its sidebands spread out either side. A receiver can successfully demodulate the data only if it receives the whole signal. In case of FDM, guard bands are inserted so that interference between the signals, resulting in cross-talks, does not occur. However, since orthogonal signals are used in OFDM, no interference occurs between the signals even if their sidebands overlap. So, guard bands can be removed, thus saving bandwidth. The criteria that need to be maintained is that the carrier spacing should be equal to the reciprocal of the symbol period.
</h4>

![image](https://user-images.githubusercontent.com/92263062/187749015-25e8511a-eaee-4940-8ef4-748358d9654c.png)

<h4>
In order that OFDM works, there should be very accurate synchronization between the communicating nodes. If frequency deviation occurs in the sub-streams, they will not be orthogonal any more, due to which interference between the signals will occur. OFDM solves the problem of channel multipath and inter symbol interference but performs miserably to tackle doppler shift during high-speed motion between transmitter and receiver.
I have implemented a full-duplex OFDM transceiver in GNU radio to transmit both mp3 and mp4 files. First image shows the flowgraph of an OFDM transceiver without separate transmitter and receiver sections. The flowgraphs of transmitter and receiver sections are shown in the next images.
</h4>

![image](https://user-images.githubusercontent.com/92263062/187749292-35ce52a9-1268-43d5-954c-6e815b479dc6.png)

![image](https://user-images.githubusercontent.com/92263062/187749307-97c4556f-0c63-4521-9550-cca594c59b39.png)

![image](https://user-images.githubusercontent.com/92263062/187749345-77f5cc5b-51db-4165-b89a-52d276507dd9.png)

<h4>
The resulting interface after executing the above flowgraph is attached below. The transmitted signal, received signal, transmitted spectrum and received spectrum are visible.
</h4>

![image](https://user-images.githubusercontent.com/92263062/187749495-ad2ebc8c-babe-48b6-b4a4-1c319cb86444.png)

![image](https://user-images.githubusercontent.com/92263062/187749515-5cff48d3-46d7-4125-853d-cea5aa71cb4a.png)


#### OTFS TRANSCEIVER: 
<h4>
The above transceivers fail to perform well in high mobility scenarios where the Doppler shifts witnessed are quite high (e.g., several kHz of Doppler). Orthogonal time–frequency space (OTFS) is a recently proposed radio access technology waveform which performs very well for high-mobility environments. It is a two-dimensional modulation scheme in which information symbols are multiplexed in the delay–Doppler domain.

Below is an example of a wireless channel in an urban multi-lane scenario illustrating the sparsity and slow variability of the channel in the delay–Doppler representation compared to time frequency representation. OTFS modulation takes advantage of slow variability of the delay doppler model of a channel.
</h4>

![image](https://user-images.githubusercontent.com/92263062/187749921-b7fa0002-2442-42ad-a8ab-9913eb713eac.png)

<h4>
The figure below shows the block diagram of the OTFS modulation scheme which is utilised to improve robustness of the signal against high doppler shifts. The inner box in the diagram shows the multicarrier modulation in the time–frequency domain and the outer box with a pre-processor and a post-processor block implements the OTFS modulation in the delay–Doppler domain.
</h4>

![image](https://user-images.githubusercontent.com/92263062/187750006-777bcbb0-5bde-4cc3-8c87-5764ffeea43e.png)

![image](https://user-images.githubusercontent.com/92263062/187750044-c6e45883-ffcc-4b3d-b54a-d36aabcdc973.png)

<h4>
I have implemented a full-duplex OTFS transceiver in GNU radio to transmit both mp3 and mp4 files. The flowgraphs of transmitter and receiver sections are shown in the following images.
</h4>

![image](https://user-images.githubusercontent.com/92263062/187750119-9c453502-4f28-462b-bc21-273586339a63.png)

![image](https://user-images.githubusercontent.com/92263062/187750153-161d8714-51bc-43a6-8e68-1d304da1df8a.png)
