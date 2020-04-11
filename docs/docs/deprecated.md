<a name="module_bcijs"></a>

## bcijs

* [bcijs](#module_bcijs)
    * ~~[.LDA](#module_bcijs.LDA)~~
        * [new LDA(class1, class2)](#new_module_bcijs.LDA_new)
        * [.project(point)](#module_bcijs.LDA.project) ⇒ <code>number</code>
    * ~~[.network](#module_bcijs.network) : <code>object</code>~~
        * [.addEEGListener(oscAddress, oscPort, eegAddress, callback)](#module_bcijs.network.addEEGListener)
    * ~~[.signal](#module_bcijs.signal) : <code>object</code>~~
        * [generate(amplitudes, frequencies, sampleRate, duration)](#generate) ⇒ <code>Array.&lt;number&gt;</code>
        * _static_
            * [.CSP](#module_bcijs.signal.CSP)
                * [new CSP(class1, class2)](#new_module_bcijs.signal.CSP_new)
                * [.project(data, [dimensions])](#module_bcijs.signal.CSP.project) ⇒ <code>Array.&lt;Array.&lt;number&gt;&gt;</code>
            * [.EEGWindow](#module_bcijs.signal.EEGWindow)
                * [new EEGWindow(size, numChannels, callback)](#new_module_bcijs.signal.EEGWindow_new)
                * [.addData(data)](#module_bcijs.signal.EEGWindow+addData)
                * [.clear()](#module_bcijs.signal.EEGWindow+clear)
            * [.getPSD(size, signal)](#module_bcijs.signal.getPSD) ⇒ <code>Array.&lt;number&gt;</code>
            * [.getBandPower(size, psd, sampleRate, band)](#module_bcijs.signal.getBandPower) ⇒ <code>number</code>
    * ~~[.averageBandPowers(samples, sampleRate, bands, [fftSize])](#module_bcijs.averageBandPowers) ⇒ <code>Array.&lt;number&gt;</code>~~
    * ~~[.f1score(confusionMatrix)](#module_bcijs.f1score) ⇒ <code>number</code>~~
    * ~~[.psd(signal, [options])](#module_bcijs.psd) ⇒ <code>Array.&lt;number&gt;</code>~~
    * ~~[.psdBandPower(psd, sampleRate, band, [fftSize])](#module_bcijs.psdBandPower) ⇒ <code>number</code>~~
    * ~~[.signalBandPower(samples, sampleRate, bands, [options])](#module_bcijs.signalBandPower) ⇒ <code>number</code>~~

<a name="module_bcijs.LDA"></a>

### ~~bcijs.LDA~~
***Deprecated***

**Kind**: static class of [<code>bcijs</code>](#module_bcijs)  

* ~~[.LDA](#module_bcijs.LDA)~~
    * [new LDA(class1, class2)](#new_module_bcijs.LDA_new)
    * [.project(point)](#module_bcijs.LDA.project) ⇒ <code>number</code>

<a name="new_module_bcijs.LDA_new"></a>

#### new LDA(class1, class2)
An LDA object


| Param | Type | Description |
| --- | --- | --- |
| class1 | <code>Array.&lt;Array.&lt;number&gt;&gt;</code> | Data set for class 1, rows are samples, columns are variables |
| class2 | <code>Array.&lt;Array.&lt;number&gt;&gt;</code> | Data set for class 2, rows are samples, columns are variables |

<a name="module_bcijs.LDA.project"></a>

#### LDA.project(point) ⇒ <code>number</code>
Predict the class of an unknown data point

**Kind**: static method of [<code>LDA</code>](#module_bcijs.LDA)  
**Returns**: <code>number</code> - value less than 0 if predicted to be in class 1, 0 if exactly inbetween, greater than 0 if class 2  

| Param | Type | Description |
| --- | --- | --- |
| point | <code>Array.&lt;number&gt;</code> | The data point to be classified. |

<a name="module_bcijs.network"></a>

### ~~bcijs.network : <code>object</code>~~
***Deprecated***

The network operations for bcijs<p>These methods are exclusive to Node.js</p>

**Kind**: static namespace of [<code>bcijs</code>](#module_bcijs)  
<a name="module_bcijs.network.addEEGListener"></a>

#### network.addEEGListener(oscAddress, oscPort, eegAddress, callback)
Calls callback when EEG data is received over the network.

**Kind**: static method of [<code>network</code>](#module_bcijs.network)  

| Param | Type | Description |
| --- | --- | --- |
| oscAddress | <code>string</code> | The address of the OSC server. For example: 127.0.0.1. |
| oscPort | <code>number</code> | The port of the OSC server. |
| eegAddress | <code>string</code> | The OSC header for the EEG data. For example: Person0/eeg. |
| callback | <code>requestCallback</code> | Called when EEG data is received. |

<a name="module_bcijs.signal"></a>

### ~~bcijs.signal : <code>object</code>~~
***Deprecated***

Signal processing operations

**Kind**: static namespace of [<code>bcijs</code>](#module_bcijs)  

* ~~[.signal](#module_bcijs.signal) : <code>object</code>~~
    * [generate(amplitudes, frequencies, sampleRate, duration)](#generate) ⇒ <code>Array.&lt;number&gt;</code>
    * _static_
        * [.CSP](#module_bcijs.signal.CSP)
            * [new CSP(class1, class2)](#new_module_bcijs.signal.CSP_new)
            * [.project(data, [dimensions])](#module_bcijs.signal.CSP.project) ⇒ <code>Array.&lt;Array.&lt;number&gt;&gt;</code>
        * [.EEGWindow](#module_bcijs.signal.EEGWindow)
            * [new EEGWindow(size, numChannels, callback)](#new_module_bcijs.signal.EEGWindow_new)
            * [.addData(data)](#module_bcijs.signal.EEGWindow+addData)
            * [.clear()](#module_bcijs.signal.EEGWindow+clear)
        * [.getPSD(size, signal)](#module_bcijs.signal.getPSD) ⇒ <code>Array.&lt;number&gt;</code>
        * [.getBandPower(size, psd, sampleRate, band)](#module_bcijs.signal.getBandPower) ⇒ <code>number</code>

<a name="generate"></a>

#### signalgenerate(amplitudes, frequencies, sampleRate, duration) ⇒ <code>Array.&lt;number&gt;</code>
Generate a signal.

**Returns**: <code>Array.&lt;number&gt;</code> - The generated signal. Equals the summation of <code>amplitudes[i] * sin(2 * pi * frequencies[i] * t)</code>.  

| Param | Type | Description |
| --- | --- | --- |
| amplitudes | <code>Array.&lt;number&gt;</code> | The amplitudes of each frequency in the signal. |
| frequencies | <code>Array.&lt;number&gt;</code> | The frequencies to be included in the signal. |
| sampleRate | <code>number</code> | The sample rate of the signal in Hz. |
| duration | <code>number</code> | The duration of the signal in seconds. |

<a name="module_bcijs.signal.CSP"></a>

#### signal.CSP
**Kind**: static class of [<code>signal</code>](#module_bcijs.signal)  

* [.CSP](#module_bcijs.signal.CSP)
    * [new CSP(class1, class2)](#new_module_bcijs.signal.CSP_new)
    * [.project(data, [dimensions])](#module_bcijs.signal.CSP.project) ⇒ <code>Array.&lt;Array.&lt;number&gt;&gt;</code>

<a name="new_module_bcijs.signal.CSP_new"></a>

##### new CSP(class1, class2)
Creates a new CSP object


| Param | Type | Description |
| --- | --- | --- |
| class1 | <code>Array.&lt;Array.&lt;number&gt;&gt;</code> | Data samples for class 1. Rows should be samples, columns should be signals. |
| class2 | <code>Array.&lt;Array.&lt;number&gt;&gt;</code> | Data samples for class 2. Rows should be samples, columns should be signals. |

<a name="module_bcijs.signal.CSP.project"></a>

##### CSP.project(data, [dimensions]) ⇒ <code>Array.&lt;Array.&lt;number&gt;&gt;</code>
Projects data and reduces to given number of dimensions

**Kind**: static method of [<code>CSP</code>](#module_bcijs.signal.CSP)  
**Returns**: <code>Array.&lt;Array.&lt;number&gt;&gt;</code> - Projected data. Rows are samples, columns are dimensions sorted by descending importance.  

| Param | Type | Description |
| --- | --- | --- |
| data | <code>Array.&lt;Array.&lt;number&gt;&gt;</code> | Data points to be projected. Rows should be samples, columns should be signals. |
| [dimensions] | <code>number</code> | Number of dimensions to be returned. Can range from 1 to number of signals. Defaults to number of signals. |

<a name="module_bcijs.signal.EEGWindow"></a>

#### signal.EEGWindow
**Kind**: static class of [<code>signal</code>](#module_bcijs.signal)  

* [.EEGWindow](#module_bcijs.signal.EEGWindow)
    * [new EEGWindow(size, numChannels, callback)](#new_module_bcijs.signal.EEGWindow_new)
    * [.addData(data)](#module_bcijs.signal.EEGWindow+addData)
    * [.clear()](#module_bcijs.signal.EEGWindow+clear)

<a name="new_module_bcijs.signal.EEGWindow_new"></a>

##### new EEGWindow(size, numChannels, callback)
Create a new EEGWindow object.


| Param | Type | Description |
| --- | --- | --- |
| size | <code>number</code> | The number of samples to be stored before callback is called. |
| numChannels | <code>number</code> | The number of channels in each sample. |
| callback | <code>requestCallback</code> | Called when the EEGWindow has a number of samples equal to size. An array of dimensions channels x samples is passed to the callback function. |

<a name="module_bcijs.signal.EEGWindow+addData"></a>

##### eegWindow.addData(data)
Adds a data sample to the EEGWindow.

**Kind**: instance method of [<code>EEGWindow</code>](#module_bcijs.signal.EEGWindow)  

| Param | Type | Description |
| --- | --- | --- |
| data | <code>Array.&lt;number&gt;</code> | The data sample to be added. Should be of length 'channels' |

<a name="module_bcijs.signal.EEGWindow+clear"></a>

##### eegWindow.clear()
Reset the EEGWindow and clear all data from it.

**Kind**: instance method of [<code>EEGWindow</code>](#module_bcijs.signal.EEGWindow)  
<a name="module_bcijs.signal.getPSD"></a>

#### signal.getPSD(size, signal) ⇒ <code>Array.&lt;number&gt;</code>
Compute the power spectral density of a given signal.

**Kind**: static method of [<code>signal</code>](#module_bcijs.signal)  
**Returns**: <code>Array.&lt;number&gt;</code> - The PSD.  

| Param | Type | Description |
| --- | --- | --- |
| size | <code>number</code> | Size of the fourier transform to be used. Should be a power of 2. |
| signal | <code>Array.&lt;number&gt;</code> | The signal. |

<a name="module_bcijs.signal.getBandPower"></a>

#### signal.getBandPower(size, psd, sampleRate, band) ⇒ <code>number</code>
Compute the average power across a given frequency band given the PSD.

**Kind**: static method of [<code>signal</code>](#module_bcijs.signal)  
**Returns**: <code>number</code> - The average power in the frequency band.  

| Param | Type | Description |
| --- | --- | --- |
| size | <code>number</code> | Size of the fourier transform used to compute the PSD. |
| psd | <code>Array.&lt;number&gt;</code> | Power spectral density of the signal. |
| sampleRate | <code>number</code> | The sample rate of the signal. |
| band | <code>Array.&lt;number&gt;</code> \| <code>string</code> | The frequency band provided as an array [frequencyStart, frequencyStop] or a string <code>delta</code> (1-3 Hz), <code>theta</code> (4-7 Hz), <code>alpha</code> (8-12 Hz), <code>beta</code> (13-30 Hz), or <code>gamma</code> (31-50 Hz). While string representations allow for easier prototyping, the use of a specific band passed as an array is recommended, as band string representations may change in future updates. |

<a name="module_bcijs.averageBandPowers"></a>

### ~~bcijs.averageBandPowers(samples, sampleRate, bands, [fftSize]) ⇒ <code>Array.&lt;number&gt;</code>~~
***Deprecated***

The functionality of this method has been replaced with the 'bandpower' method.See the docs for 'bandpower' for more information.Computes the average magnitude across each frequency band averaged across all channelsUnits are that of the input signal. For example, if the input signal is measuredin μV, then this method returns values in μV.

**Kind**: static method of [<code>bcijs</code>](#module_bcijs)  
**Returns**: <code>Array.&lt;number&gt;</code> - Array containing the average power across all channels in each band  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| samples | <code>Array.&lt;Array.&lt;number&gt;&gt;</code> |  | The signals where rows are samples and columns are electrodes |
| sampleRate | <code>number</code> |  | Sample rate of the data |
| bands | <code>Array</code> |  | An array of frequency bands. See signalBandPower for more info on frequency bands. |
| [fftSize] | <code>number</code> | <code></code> | The size of the fft to use. See signalBandPower for more info on fft sizes. |

**Example**  
```js
let feature = bci.averageBandPowers(samples, 256, ['alpha', 'beta']);// returns [alpha_power_averaged_across_channels, beta_power_averaged_across_channels]
```
<a name="module_bcijs.f1score"></a>

### ~~bcijs.f1score(confusionMatrix) ⇒ <code>number</code>~~
***Deprecated***

Calculate the f1 score of a binary classifier given its confusion matrixThis method uses the following definition of a confusion matrix:C = [  [true positive, false negative],  [false positive, true negative]]which does not match the definition provided by the method bcijs.confusionMatrix.As such, it has been deprecated and replaced with the method bcijs.f1 in order to prevent a version breaking change.

**Kind**: static method of [<code>bcijs</code>](#module_bcijs)  
**Returns**: <code>number</code> - The f1 score  

| Param | Type | Description |
| --- | --- | --- |
| confusionMatrix | <code>Array.&lt;Array.&lt;number&gt;&gt;</code> | a 2x2 confusion matrix |

<a name="module_bcijs.psd"></a>

### ~~bcijs.psd(signal, [options]) ⇒ <code>Array.&lt;number&gt;</code>~~
***Deprecated***

The functionality of this method has been replaced with the 'periodogram' method.See the docs for 'periodogram' for more information.Computes the magnitude of each frequency bin of the FFT. Units are that of the input signal.For example, if the input signal is measured in μV, then this method returns values in μV.As a PSD (particularly for EEG data) would be expected to return units of μV^2/Hz, this method hasbeen deprecated to avoid confusion. It has been replaced with the periodogram method, which returns unitsof μV^2/Hz.

**Kind**: static method of [<code>bcijs</code>](#module_bcijs)  
**Returns**: <code>Array.&lt;number&gt;</code> - magnitude of each frequency bin of the FFT  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| signal | <code>Array.&lt;number&gt;</code> |  | The signal. |
| [options] | <code>Object</code> |  |  |
| [options.fftSize] | <code>number</code> | <code>Math.pow(2, bci.nextpow2(signal.length))</code> | Size of the fft to be used. Should be a power of 2. |
| [options.truncate] | <code>boolean</code> | <code>false</code> | If true, only the first half of the PSD array is returned |

<a name="module_bcijs.psdBandPower"></a>

### ~~bcijs.psdBandPower(psd, sampleRate, band, [fftSize]) ⇒ <code>number</code>~~
***Deprecated***

The functionality of this method has been replaced with the 'bandpower' method.See the docs for 'bandpower' for more information.Computes the average magnitude across each frequency band given the output of the PSD method.Units are that of the input signal. For example, if the input signal is measuredin μV, then this method returns values in μV.Compute the average power across a given frequency band given the PSD.

**Kind**: static method of [<code>bcijs</code>](#module_bcijs)  
**Returns**: <code>number</code> - The average power in the frequency band.  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| psd | <code>Array.&lt;number&gt;</code> |  | Power spectral density of the signal. |
| sampleRate | <code>number</code> |  | The sample rate of the signal. |
| band | <code>Array.&lt;number&gt;</code> \| <code>string</code> |  | The frequency band provided as an array [frequencyStart, frequencyStop] or a string <code>delta</code> (1-3 Hz), <code>theta</code> (4-7 Hz), <code>alpha</code> (8-12 Hz), <code>beta</code> (13-30 Hz), or <code>gamma</code> (31-50 Hz). While string representations allow for easier prototyping, the use of a specific band passed as an array is recommended, as band string representations may change in future updates. |
| [fftSize] | <code>number</code> | <code>Math.pow(2, bci.nextpow2(psd.length))</code> | Size of the fourier transform used to compute the PSD. |

<a name="module_bcijs.signalBandPower"></a>

### ~~bcijs.signalBandPower(samples, sampleRate, bands, [options]) ⇒ <code>number</code>~~
***Deprecated***

The functionality of this method has been replaced with the 'bandpower' method.See the docs for 'bandpower' for more information.Computes the average magnitude across each frequency band.Units are that of the input signal. For example, if the input signal is measuredin μV, then this method returns values in μV.

**Kind**: static method of [<code>bcijs</code>](#module_bcijs)  
**Returns**: <code>number</code> - The average power in the frequency band.  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| samples | <code>Array.&lt;number&gt;</code> \| <code>Array.&lt;Array.&lt;number&gt;&gt;</code> |  | The signal (array of numbers) or a matrix of signals, where rows are samples and columns are signals. |
| sampleRate | <code>number</code> |  | The sample rate of the signal. |
| bands | <code>Array</code> \| <code>string</code> |  | The frequency band or array of bands, where a single band is provided as an array [frequencyStart, frequencyStop] or a string <code>delta</code> (1-3 Hz), <code>theta</code> (4-7 Hz), <code>alpha</code> (8-12 Hz), <code>beta</code> (13-30 Hz), or <code>gamma</code> (31-50 Hz).<br> While string representations allow for easier prototyping, the use of a specific band passed as an array is recommended, as band string representations may change in future updates. |
| [options] | <code>Object</code> |  |  |
| [options.fftSize] | <code>number</code> | <code>Math.pow(2, bci.nextpow2(signal.length))</code> | Size of the fft to be used. Should be a power of 2. |

**Example**  
```js
// Example outputs are rounded// Single signal exampleslet sampleRate = 512;let signal = bci.generateSignal([2,16], [10,20], sampleRate, 1);// Get a single power in one bandconsole.log(bci.signalBandPower(signal, sampleRate, 'alpha')); // returns 102.4// Specify a custom band as an array (Ex: 8 Hz - 12 Hz)console.log(bci.signalBandPower(signal, sampleRate, [8, 12])); // returns 102.4// Obtain multiple band powersconsole.log(bci.signalBandPower(signal, sampleRate, ['alpha', 'beta'])); // returns [ 102.4, 227.6 ]// Multiple band powers works with custom bands tooconsole.log(bci.signalBandPower(signal, sampleRate, [[8, 12], [13, 30]])); // returns [ 102.4, 227.6 ]// Works with multiple signals too (example with 2 signals)let signal2 = bci.generateSignal([16, 2], [10, 20], 512, 1);let samples = bci.transpose([signal, signal2]);console.log(bci.signalBandPower(samples, sampleRate, 'alpha'));// Returns an array containing the alpha value for each signalconsole.log(bci.signalBandPower(samples, sampleRate, ['alpha', 'beta', 'gamma']));// Returns a 2d array with number_of_bands rows and number_of_signals columns
```
