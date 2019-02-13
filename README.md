# pytorch-tvnet
This project is pytorch implementation of TVNet in ['End-to-End Learning of Motion Representation for Video Understanding'](http://lijiefan.me/project_webpage/TVNet_cvpr/papers/TVNet_cvpr.pdf) with *pytorch-style*.

The original implementation was in tensorflow, which is in https://github.com/LijieFan/tvnet.

# Requirements
**Python 2.7**: can support python 3.x by easily changing *xrange* function to *range*.

**pytorch** 

**matlab (optinonal)**: In the original tensorflow version, authors use `.mat` file for TVNet generated results saving, and `Matlab` for results [`visualization`](http://sintel.is.tue.mpg.de). In the demo code, I also add code for visulizing flow map using cv2 (a python libarry).
 
# Usage
#### I) Put input frames in `frame/img1.png`, `frame/img2.png`.
#### II) Use TVNet to generate motion representation 

The file (`demo.py`) has the following options:
- `-scale`: Number of scales in TVNet (default: 1)
- `-warp`: Number of warppings in TVNet (default: 1)
- `-iteration`: Number of iterations in TVNet(default: 50)
- `-gpu`: the gpu to run on (0-indexed, -1 for CPU)

Sample usages include
- Generate motion representation for frames in `frame/img1.png` and `frame/img2.png`.

```
python demo.py --scale 1 --warp 1 --iteration 50 --gpu 1
``` 

#### III) Check results and visualization

-TVNet generated results are saved in `result/result-pytorch.mat`

-Use the MPI-Sintel tool box for result visualization. In matlab, run ```run visualize/visualize.m```, or in python, use code attached in the bottom of demo.py.


# Sample input
<table>
<tr>
<td><img src="frame/img1.png" height="160"></td>
<td><img src="frame/img2.png" height="160"></td>
</tr>
</table>

# Sample output
<table>
<tr>
<td><img src="result/result.png" height="160"></td>
<td><img src="result/result-pytorch.png" height="160"></td>
</tr>
<tr>
<td>tensorflow</td>
<td>pytorch</td>
</tr>
</table>
