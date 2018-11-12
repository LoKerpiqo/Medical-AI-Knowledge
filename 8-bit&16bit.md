# 8-bit and 16-bit and 二值图像
图像的位数通常8位，2^ 8=256. 但实际上，图片也可以有单通道16位，或单通道32位，不过通常数据量太大，意义有限。一张单通道8位彩色图有三个通道，R、G、B。
例如彩色图的一个像素点RGB（254，100，76）
彩色图可以转为黑白图像 **Gray = R * 30% + G * 59% + B * 11%, Gray = 254 * 30% + 100 * 59% + 76*11% = 144** ,至此，三通道转化为了单通道。

现在，单通道转0-1二值图像。
选定一个**threshold**，往上为纯白255,但是此处映射为1，**因为255需要8位编码存储，浪费内存**，**往下为纯黑0**。

# Pixel and Voxel

A pixel represents the smallest sampled 2D element in an image. It has dimensions given along two axes in mm, dictating in-plane spatial resolution. Pixel sizes range in clinical MRI from mm to sub-mm. A voxel is the colume element, defined in 3D place. It dimensions are ghiven by the pixel, together with the thickness of the slice (the measurement along the third axis). Sluce thicknesses in clinical MRI vary fron a maximum near 5 mm, achieved using 2D multisclice imaging, to sub-mm, achieved with 3D scan tech.

**MRI Spatial Resolution**, which determines the radiologist's ability to distinguish structures as separate and distinct from each other ( together with image contrast), is inherently related to the **acquired voxel volume**. In the simplest case, 

>**The field of view**(FOV), acquisition matrix, and the sclice thickness determine voxel volume. The **pixel size = FOV/matrix**, determines the in-plane resolution. **Reducing the FOV, incresing the matrix number, or reducing the slice thickness results in an image with reduced voxel volume**. 

**Signal-to-noisy-Ratio (SNR)** is *directly proportional* to **voxel size** (assuming that the number of phase encoding steps is held constant). Small voxels produce MRI images with high spatial resolution but a lower signal-to-noisy ratio, and thus may appear "grainy" compared with images acquired with a larger voxel volume.

>更小的体素（更薄z更小xy）可以得到更高的spatial resolution，但与此同时会得到更低的SNR（信号噪音比下降，看起来更加多的纹理‘grainy’）
![image](https://github.com/LoKerpiqo/Medical-AI-Knowledge/tree/master/img/xy.JPG)

>更thinner，图片2
![image](https://github.com/LoKerpiqo/Medical-AI-Knowledge/tree/master/img/thickness.JPG)


