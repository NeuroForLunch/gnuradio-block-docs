# gr-doppler

Python block that gives the doppler factor. It uses [orbit-predictor](https://github.com/satellogic/orbit-predictor).


###Installation

```
pip install orbit-predictor
mkdir build
cd build
cmake ../
make
sudo make install
```

Note: If you are running MacPorts you might need to change the installation
path. Use something like this: `cmake -DCMAKE_INSTALL_PREFIX=/opt/local ../`