### Intro

The preprocessing workflow includes the signal processing, window selection and construct adjoint sources. I have a github
repo, [pytomo3d](https://github.com/wjlei1990/pytomo3d) that you should install first if you want to get familiar about what
we are doing right now. It wraps those functions together. So please follow the 
[INSTALL.md](https://github.com/wjlei1990/pytomo3d/blob/master/INSTALL.md) files in that repo to install things first.

##### 1. Signal processing
We are currently using `pytomo3d.signal` to do the signal processing. But under the hood it is obspy. 
If you want to get familiar with obspy, the doc is [here](https://docs.obspy.org/tutorial/). Under the 
hood means we are calling obspy APIs in pytomo3d, but we wrap it up for our needs.

In pytomo3d, we wrap obspy and create the API we would use: https://github.com/wjlei1990/pytomo3d/blob/master/pytomo3d/signal/process.py#L160

##### 2. Window selection
We are currently using `pytomo3d.window` but under the hood it is [pyflex](http://krischer.github.io/pyflex/).

The window APIs in pytomo3d is: https://github.com/wjlei1990/pytomo3d/blob/master/pytomo3d/window/window.py#L113

#### 3. Adjoint source
We are using `pytomo3d.adjoint` but under the hood it is [pyadjoint](http://krischer.github.io/pyadjoint/). 

The adjoint APIs in pyadjoint is: https://github.com/wjlei1990/pytomo3d/blob/master/pytomo3d/adjoint/adjsrc.py#L146

As the starting point, I suggest you to use sac data format, which is more flexible and easy to handle. After you get familiar
with all these tools, you can try to move our new data format, `ASDF`.
