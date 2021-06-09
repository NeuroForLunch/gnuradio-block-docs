

The module is capable of the following:
- Energy detection of continuous signals
- Filtering of detected signals
- OFDM parameter estimation (carrier spacing, symbol time)
- Blind OFDM synchronization
- Resampling of signals to constant rate
- 3D Visualisation of FAM data, from gr-specest (not on GR 3.8 yet)
- Using TensorFlow models for AMC (not on GR 3.8 yet)

## Usage
Get inspired by the examples. There are flowgraphs for each block that should explain how to use them.

For detailed information about each block, visit the Doxygen HTML pages.
## Brief block description

A typical inspector flowgraph could look like this:
https://grinspector.files.wordpress.com/2016/05/decentral.png

#### Signal Detector
Performs an energy detection of continuous input signals. A threshold in dB can be set or an autmatic threshold calculation can be used.

#### Inspector GUI
GUI where the spectrum is displayed along with signal markers for the detected signals. Also, signal can be selected manually in this block.

#### Signal Separator
Takes the signal info from the previous blocks and performs a down-mixing, filtering and decimation of each detected signal. The samples for each signal are passed on as a message.

#### Signal Extractor
Adapter block to extract the samples of one signal out of the messages from the Signal Separator. Output is again a complex stream.

Resampling can be used to assure a constant output sample rate of the stream. (Needed for FM demod for instance.)

#### OFDM Estimator
Estimates the parameters subcarrier spacing, symbol time, FFT size and cyclic prefix length for a input signal. The signal should not be oversampled for this block.

#### OFDM Synchronizer
After OFDM parameter estimation, the signal is frequency synced and symbol beginnings are marked with stream tags.

The target is to develop a signal analysis / signal intelligence toolbox with the following capabilities:

- Automatic signal detection
- Automatic modulation classification
- OFDM parameter estimation and synchronization
- GUI feedback
- Doxygen documentation

Read the full proposal here https://github.com/sbmueller/gsoc-proposal/blob/master/sigint-proposal.pdf.

The modulation classification is developed by @chrisruk during ESA Summer of Code in Space program.

## Contact/Help
If you run into problems installing or using gr-inspector, the GNU Radio [mailing list](https://wiki.gnuradio.org/index.php/MailingLists) is the right place to get help. There are many people who will provide assistance. **Please do provide a complete problem description containing**

1. What exactly where you trying to do?
2. What steps did you perform to achieve this?
3. What happened (with complete verbose output)?
4. Why do you think something went wrong? What should have happened instead?

Visit [How to report errors](https://wiki.gnuradio.org/index.php/ReportingErrors) for more detailed instructions.

**Please only use GitHub issues for actual bugs and improvements!** "This command is not working on my machine" is not a bug.

Maintainer of this module:

Sebastian Müller<br/>
gsenpo[at]gmail.com

Christopher Richardson<br/>
chrisrichardsonuk[at]gmail.com

If you want to know more about the development process, please visit the [blog](https://grinspector.wordpress.com/).
