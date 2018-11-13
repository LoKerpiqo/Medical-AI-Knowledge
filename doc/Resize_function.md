# A detailed description for Skimage function
https://www.jianshu.com/p/f2e88197e81d

# An example for medical image preprocessing
https://blog.csdn.net/u013635029/article/details/72957944

# Matlab Resize function
http://www.itdaan.com/blog/2012/09/21/d984f2be9ec91e9f9e7e734fed54f10b.html

******
we are trying to resize our CT images into a uniform 3-dimension size, e.g. [128,128,128]. Say we now have [512,512,326] CT images. There are several ways founded to achieved it.
#### method 1 : SimpleITK by set Spacing and Size to selecting fewer slices.
<pre><code>import SimpleITK as sitk

s = sitk.ReadImage(PATH)
s.GetSize() #512*512*326
s.GetOrigin() #0,0,0
s.GetSpacing() # 1,1,1
s.GetDirection() # x,y,z

# The spatial definition of the images we want to use in a dl framework (smaller than the original)
new_size = [128,128,128]
reference_image = sitk.Image(new_size,s.GetPixelIDValue())
reference_image.SetOrigin(s.GetOrigin())
reference_image.SetDirection(s.GetDirection())
reference_image.SetSpacing([sz * spc/nsz for nsz,sz,spc in zip(new_size,s.GetSize(),s.GetSpacing())])

# Resample without any smoothing
cropped = sitk.Resample(s,reference_image)
</code></pre>
In this method, the pixel value will keep the same range as original image. 

#### method 2 : Use skimage read .tif and then transform it. (data type is numpy)
<pre><code>from skimage import transform
from skimage import io

img = io.imread(PATH, plugin = 'simpleitk')
timg = transform.resize(img, (128,128,128),order = 2)
</code></pre>
In this method, the pixel value will be squeezed into a very small range. e.g. timg.max() = 0.044 but img.max() = 4k

#### method 3 : Use matlab resize3 and interp3 
