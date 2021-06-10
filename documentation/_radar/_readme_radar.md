`git clone https://github.com/kit-cel/gr-radar.git` // clone this repository
`cd gr-radar/`
`mkdir build` // make build folder
`cd build/`
`cmake ../` // build makefiles
`make` // build toolbox

Some test cases use huge buffer sizes. Therefore you have to increase the maximum size of a single shared memory segment. Run following line to fix that. Additionally the script configures some USRP stuff. All changes will be reset after reboot.

`sudo ./../examples/setup/setup_core`

Now you can run all testcases and install the toolbox. If `ctest` responds with '100% tests passed' the toolbox should be build correctly.

`ctest` // run tests
`sudo make install` // install toolbox

**Development progress blog**
https://grradar.wordpress.com/

**Documentation**
For full documentation build the toolbox and open `build/docs/doxygen/html/index.html` in any web browser.


**Development platform**
GNU Radio maint-3.8
UHD 3.15
Ubuntu 18.04

**Contact**
Stefan Wunsch
stefan.wunsch[at]student.kit.edu