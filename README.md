# Java support to EDF files

The repository implements the following package:

``` java
package br.unb.biologiaanimal.edf;
```

which provides an interface with EDF files for the Java programming language, so we can use them in our MATLAB applications. The produced Jar file enables the deconstruction of an EDF file into its header and its records; so the raw records can be directly accessed or translated to ASCII friendly formats.

Although it is already being used, this code is work in progress and shall be used carefully.

Help and ideas are always welcome! `:)`

## The `EDF` class ##

Those are the currently available methods for this class.

### Methods ###

#### `public EDF(String filePath)` ####

This is the constructor. It requires a string that describes the path to the

#### `public String getFile()` ####

- Gets the file path.
- Return: the file path;

#### `public HashMap getHeader()` ####

- Gets raw EDF header.

#### `public HashMap getRecords()` ####

- Gets raw EDF records

#### `public String[] getLabels()` ####

- Get the labels contained in this EDF file.

#### `public int getSamplingRate()` ####

- Gets the sampling rate of the recording.


#### `public void toAscii(String filePath) throws IOException` ####

- Formats the read records into the ASCII format and saves it into memory.
- Paramter `filePath`: the path to the file to be written.

#### `public void toSingleChannelAscii(String filePath, String channel) throws IOException` ####

* Writes a determined record to a file.
* Parameter `filePath`: the path to the file to be written
* Parameter `channel`: the label of the record to be saved on memory


#### `public String[] getAnnotations() throws NoSuchFieldException` ####

* Gets a list of the annotations on the EDF file, lest there are annotations.
* Returns an array containing one annotation for each entry.

#### `public double getConvertionFactor(String label)` ####

* Gets the convertion factor related to the given label
* Paramter `label`: the channel's label whose convertion factor we want
* Returns the convertion factor.

#### `public double[] getSignal(String label)` ####

* Get a signal based on its label.
* Parameter `label`: the signal label.
* Returns the translated record.
