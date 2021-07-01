# DSP project </br>  Audio-and-Image-Processing

This project is to practice processing audio and image signal. For audio signal processing practice, we made Gaussian noise by ourselves and then, remove it by hanning windowing and lowpass filter using pole-zero placement. For image signal processing, we set the original image and noised image. To remove the noise, we applied an ideal lowpass filter and highpass filter, and compare them to the gaussian filter and laplacian filter.</br></br>

## Audio signal processing
<p align="center">
<img src = "https://github.com/mayshin10/Audio-and-Image-Signal-Processing/blob/main/img_src/Filtered%20Images.png" width = "600px" ></br>
Original audio signal and gaussian nosie(N(0, 0.02))</br></br>
<img src = "https://github.com/mayshin10/DSP-FPGA/blob/main/img_src/Zynq%20Board%20Results.png" width = "600px" ></br>
Truncated sinc function.
<img src = "https://github.com/mayshin10/DSP-FPGA/blob/main/img_src/Zynq%20Board%20Results.png" width = "600px" ></br>
FIR lowpass filter with 39 point Hanning window.
<img src = "https://github.com/mayshin10/DSP-FPGA/blob/main/img_src/Zynq%20Board%20Results.png" width = "600px" ></br>
Reduced noise by FIR lowpass filter with 39 point Hanning window.
<img src = "https://github.com/mayshin10/DSP-FPGA/blob/main/img_src/Zynq%20Board%20Results.png" width = "600px" ></br>
Lowpass filter designed by pole-zero placement

</br></br>

</p></br>

## Image signal processing
<p align="center">
<img src = "https://github.com/mayshin10/Audio-and-Image-Signal-Processing/blob/main/img_src/Filtered%20Images.png" width = "600px" ></br>
A original image</br></br>
<img src = "https://github.com/mayshin10/DSP-FPGA/blob/main/img_src/Zynq%20Board%20Results.png" width = "600px" ></br>
Ideal lowpass filter and highpass filter.
<img src = "https://github.com/mayshin10/DSP-FPGA/blob/main/img_src/Zynq%20Board%20Results.png" width = "600px" ></br>
Images applied ideal filters.
<img src = "https://github.com/mayshin10/DSP-FPGA/blob/main/img_src/Zynq%20Board%20Results.png" width = "600px" ></br>
Laplacian and gaussian filter.
<img src = "https://github.com/mayshin10/DSP-FPGA/blob/main/img_src/Zynq%20Board%20Results.png" width = "600px" ></br>
Compare ideal lpf to gaussian filter.
<img src = "https://github.com/mayshin10/DSP-FPGA/blob/main/img_src/Zynq%20Board%20Results.png" width = "600px" ></br>
Compare ideal hpf to laplacian filter.

</br></br>

</p></br>
