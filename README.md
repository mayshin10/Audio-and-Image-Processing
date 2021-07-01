# Audio-and-Image-Processing <br/> DSP project for processing audio signal and image signal

This project is to practice processing audio and image signal. For audio signal processing practice, we made gaussian noise by ourselves and then, remove it by hanning windowing and lowpass filter using pole-zero placement. For iamge signal processing, we set original image and noised image. To remove the noise, we applied ideal lowpass filter and highpass filer, and compare to gaussian filter and laplacian filter.</br>

## Audio signal processing
<p align="center">
<img src = "https://github.com/mayshin10/Audio-and-Image-Signal-Processing/blob/main/img_src/Filtered%20Images.png" width = "600px" ></br>
Original audio signal and gaussian nosie(N(0, 0.02))</br></br>
<img src = "https://github.com/mayshin10/DSP-FPGA/blob/main/img_src/Zynq%20Board%20Results.png" width = "600px" ></br>
Truncated sinc function.

```
$$h_d[n] = w_c/\pi sin[w_c n]/w_cn , n = 0, 1, ..., N-1 (w_c = \pi/4, N= 39)$$ 
```
</br></br>

</p></br>



## Image filtering
 The digital signal processor has to meet the following requirements. First of all, it has three filtering modes to process an image; edge, sharp, and blur. Image filtering is implemented through 1-D convolution. Each filtering mode has their convolution coefficient as follow.</br>
```
𝐸𝑑𝑔𝑒 𝐹𝑖𝑙𝑡𝑒𝑟′𝑠 1𝐷 𝑐𝑜𝑒𝑓𝑓𝑖𝑐𝑖𝑒𝑛𝑡 = [ −1, −2, 6, −2, −1]  
𝑆h𝑎𝑟𝑝 𝐹𝑖𝑙𝑡𝑒𝑟′𝑠 1𝐷 𝑐𝑜𝑒𝑓𝑓𝑖𝑐𝑖𝑒𝑛𝑡 = [−1, −2, 7, −2, −1] 
𝐵𝑙𝑢𝑟 𝐹𝑖𝑙𝑡𝑒𝑟′𝑠 1𝐷 = [0.1, 0.2, 0.4, 0.2, 0.1] 
```
 The size of the reference image we need to process is 480x272 with 16 bits per one pixel. And the edge of the image will be zero-padded for ease of calculation. It means the value of Reference Image[x] will be zero if x is less than zero or larger than 480*272-1 in the following equation.</br>
 ```
𝐹𝑖𝑙𝑡𝑒𝑟𝑒𝑑 𝐼𝑚𝑎𝑔𝑒[𝑖] = (𝑐𝑜𝑒𝑓𝑓[0] ∗ 𝑅𝑒𝑓𝑒𝑟𝑒𝑛𝑐𝑒 𝐼𝑚𝑎𝑔𝑒[𝑖 − 2])  + 
                 (𝑐𝑜𝑒𝑓𝑓[1] ∗ 𝑅𝑒𝑓𝑒𝑟𝑒𝑐𝑛𝑐𝑒 𝐼𝑚𝑎𝑔𝑒[𝑖 − 1]) +
                 (𝑐𝑜𝑒𝑓𝑓[2] ∗ 𝑅𝑒𝑓𝑒𝑟𝑒𝑛𝑐𝑒 𝐼𝑚𝑎𝑔𝑒[𝑖])      +
                 (𝑐𝑜𝑒𝑓𝑓[3] ∗ 𝑅𝑒𝑓𝑒𝑟𝑒𝑐𝑒 𝐼𝑚𝑎𝑔𝑒[𝑖 + 1])   +
                 (𝑐𝑜𝑒𝑓𝑓[4] ∗ 𝑅𝑒𝑓𝑒𝑟𝑒𝑐𝑒 𝐼𝑚𝑎𝑔𝑒[𝑖 + 2])
```
 Each RGB value has to calculate separately, and it is handled as zero when it occurs overflow.</br></br>

## Hardware
<p align="center">
<img src = "https://github.com/mayshin10/DSP-FPGA/blob/main/img_src/hardware%20architecture.png" width = "500px" ></br>
Hardware architecture</br></br>
<img src = "https://github.com/mayshin10/DSP-FPGA/blob/main/img_src/system%20wrapper.png" width = "800px" ></br>
System wrapper block diagram</br></br>

</p></br>



## Firmware
<p align="center">
<img src = "https://github.com/mayshin10/DSP-FPGA/blob/main/img_src/firmware%20control.png" width = "500px" ></br>
Firmware control logic</br></br>
</p></br>



## Results
<p align="center">
<img src = "https://github.com/mayshin10/DSP-FPGA/blob/main/img_src/Filtered%20Images.png" width = "600px" ></br>
Filtered Images</br></br>
<img src = "https://github.com/mayshin10/DSP-FPGA/blob/main/img_src/Zynq%20Board%20Results.png" width = "600px" ></br>
Zynq Board results</br></br>

</p></br>
