- Enrico Lupi
- Alessio Saccomani
- Emanuele Sarte
- Giovanni Zago

-----------------------

# Respiratory Rate Estimation

Final project for *Laboratory of Computational Physics (Mod. A)* course, Physics of Data degree at University of Padova.

## Description

Seismocardiography ([SCG](https://www.ncbi.nlm.nih.gov/pubmed/24111357)) is a very promising technique to measure Heart Rate (HR) and Respiratory Rate (RR) with the detector positioned above sternum. It is generally based on accelerometer and gyroscope readings or a combination of them. Ballistocardiography ([BCG](https://en.wikipedia.org/wiki/Ballistocardiography)) is an another technique to estimate heart and respiratory rate with combination of both accelerometer and gyroscope. It is an indirect evaluation of HR and RR since the contact between the device and the body of the subject is not required (e.g., accelerometer platform mounted under the slats of the bed). MuSe (Multi-Sensor miniaturized, low-power, wireless IMU) is an Inertial Measurement Unit ([IMU](https://en.wikipedia.org/wiki/Inertial_measurement_unit)) provide by [221e](https://www.221e.com). In the context of this project, it allows to record the inertial data necessary for the estimation of SCG and BCG. The goal of this assignment is to estimate the respiratory rate of an healthy subject, given linear acceleration and angular velocity measurements recorded by using the aforementioned MuSe platform. The study must be performed on two datasets: the first is the compulsory one (center_sternum.txt) while the second is left at the discretion of the group, among those made available for the assignment. <br>
N.B.: Remember that normal beat is around 40-100 bpm.

[Actigraphy](https://en.wikipedia.org/wiki/Actigraphy) is a non-invasive method of monitoring human rest/activity cycles. Data will be provided from sensors gathering data on humans during their day/night activities

## Datasets

The data is provided in .txt files. During this study two healthy subjects were involved with their informed consent. The first dataset was recorded on one subject, while all the other datasets were recorded on the second subject.

This is the first mandatory file:

- center_sternum.txt: MuSe placed on the center of the sternum. The subject was lying supine on his left and right side, respectively.

Choose one of the following files in order to complete the task:

1. 1_Stave_supine_static.txt: Sensor placed on a bed stave, under the mattress at the level of the chest. The subject was lying supine on his left and right side.
2. 2_Mattress_supine.txt: Sensor placed on the mattress, near one corner but not under the pillow. The subject laid in the same position as above.
3. 3_Subject_sitting_chair.txt: Sensor placed on the desk: the subject, sitting on a chair, leaned forearms and hands on the desk.
4. 4_Chest_sweater.txt: Sensor placed on the subject chest directly on a sweater.
5. 5_Under_chair.txt: Subject sitting on a chair, sensor placed under the seat of the chair.
   
All .txt files give 16 columns index, in particular:

- Log Freq stands for the acquisition in Hz (i.e., sampling interval is constant).
- AccX, AccY, AccZ are the measured magnitude of linear acceleration along each axis.
- GyroX, GyroY, GyroZ are the measured magnitude of angular velocity along each axis.
- MagnX, MagnY, MagnZ are the measured magnitude of magnetic field along each axis.
- qw, qi, qj, qk are the quaternion components, representing the spatial orientation of the Muse system.

Each dataset includes, in addition to the data, one file containing the adopted configuration of the MuSe (README1.txt for the first measurement, and in README_5.txt for the other measurement).

## Assignment

### Data preparation:

1.1. Load the txt file and select only the columns you are interesting in, in order to do a complete data analysis (e.g. Log Freq, AccX, ... )

1.2. Plot selected data in function of time and choose a properly time window over which to perform the analysis. Pay attention on time rappresentation and the measurament unit.

1.3. In order to make an appropiate work, decide if take care about some particular axis or some combination of them as well as derived features for the next step of the task. Motivate your choice.

### Time and frequency analysis:

2.1. Statistical analysis: provide a statistical description of the chosen dataset. Statistical descriptors includes for example mean, median, variance, standard deviation, 25th and 75th percentiles, and correlation coefficients. Investigate what could be the most interesting descriptors for this type of data, motivating the choices.

2.2. Fourier Analysis: Perform a frequency analysis of the data. Look at the spectrum and explain what you see. Use this step in order to properly design the filters in the following step.

### Filter:

Implement your own filter, trying to extrapolate respiratory rate signal. Hint:

(a) Directly from Fourier Analysis, antitrasform data looking for the most interesting frequency band.

(b) Choose the appropriate Lowpass/Bandpass/Highpass filter.

(c) Wavelet trasform (a powerfull instrument that make a time and frequency analysis of signal). (d) Find another method by yourselves.

Motivate your choice.

### Metrics:

4.1. Respiratory Rate Per Minute(RPM): extrapolate RPM, make an histogram of the result. Does it follow a partiular distribution?

4.2. Respiratory Rate Variability(RRV): extrapolate RRV, explain why this parameter is important, and plot the results.

### (OPTIONAL) Algorithm:

Elaborate a simple algorithm to extrapolate respiratory rate even when filter failed (e.g. look at particular threshold...).

### Conclusion:

Summarise the obtained results, in particular making a comparison between the two files analysed. Highlight limitation and critical issues encountered during the work, motivating the most relevant contribution given by your solution.
