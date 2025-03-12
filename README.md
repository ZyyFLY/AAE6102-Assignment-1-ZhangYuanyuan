# GNSS SDR Signal Processing and Analysis

## **Task 1: Acquisition**

### **Objective**
Process the IF data using a GNSS SDR to identify visible satellites and generate the initial acquisition results.

### **1.Open-sky**
![image](https://github.com/ZyyFLY/AAE6102-Assignment-1-ZhangYuanyuan/blob/main/images/1-open.png)  
- The **Acquisition Results Plot** shows that satellites with PRN 3,4,8,16, 22,26, 27, 31and 32 were successfully acquired with high acquisition metrics.

### **2.Urban**
- **Figure 2 (Acquisition Results Plot)**:
- The **Acquisition Results Plot** shows that satellites with PRN 3,4,8,16, 22,26, 27, 31and 32 were successfully acquired with high acquisition metrics.


## **Task 2: Tracking**

### **Objective**
Adapt the tracking loop (DLL) to generate correlation plots and analyze tracking performance. Discuss the impact of urban interference on correlation peaks.

### **1.Open-sky**
![image](https://github.com/ZyyFLY/AAE6102-Assignment-1-ZhangYuanyuan/blob/main/images/1-open.png)  
- The **Acquisition Results Plot** shows that satellites with PRN 3,4,8,16, 22,26, 27, 31and 32 were successfully acquired with high acquisition metrics.

### **2.Urban**
- **Figure 2 (Acquisition Results Plot)**:
- The **Acquisition Results Plot** shows that satellites with PRN 3,4,8,16, 22,26, 27, 31and 32 were successfully acquired with high acquisition metrics.
### **Results**
- **Correlation Peaks**:
  - The tracking loop maintained synchronization with the acquired satellites.
  - The correlation peaks for Prompt correlators were sharp, indicating successful tracking.
- **Impact of Urban Interference**:
  - Urban environments introduce interference that may degrade the correlation peaks, causing them to flatten or shift.
  - Multipath effects can lead to secondary peaks, potentially affecting code phase estimation.

### **Analysis Based on Plots**
- **Figure 1 (Time Domain Plot)**:
  - Shows the amplitude of the raw GNSS signal in the time domain. The signal appears noisy, which may impact correlation performance.
- **Figure 1 (Frequency Domain Plot)**:
  - Displays the frequency spectrum of the signal, showing peaks that correspond to the carrier frequencies of satellites. Noise and interference are also visible.
- **Figure 1 (Histogram Plot)**:
  - Confirms the distribution of signal samples. The near-uniform distribution suggests a well-received signal but may contain noise.

### **Discussion**
- The tracking performance is robust for the acquired satellites, with minimal distortion observed in correlation peaks.
- Advanced tracking techniques, such as Narrow Correlator or Multipath Estimating DLL, could further mitigate urban interference.

---

## **Task 3: Navigation Data Decoding**

### **Objective**
Decode the navigation message and extract key parameters, such as ephemeris data, for at least one satellite.

### **Results**
- Navigation data was successfully decoded for the tracked satellites.
- **Extracted Ephemeris Data**:
  - Semi-major axis, orbital inclination, and satellite clock corrections were obtained.
  - Satellite positions were computed based on the decoded ephemeris.

### **Analysis Based on Plots**
- **Navigation Results Derived from Tracking Data**:
  - Although not explicitly shown in the provided plots, the decoded navigation data is directly used in Figure 3 (Coordinates Variations Plot, 3D Position Plot, and Skyplot) to compute satellite positions and the receiver's location.

### **Discussion**
- Accurate decoding of navigation messages is critical for position and velocity estimation.
- Weak signals or interference can introduce errors in navigation data, which may propagate to position solutions.

---

## **Task 4: Position and Velocity Estimation**

### **Objective**
Using pseudorange measurements from tracking, implement the Weighted Least Squares (WLS) algorithm to compute the user's position and velocity.

### **Results**
- **Position Plot in UTM System**:
  - The **Coordinates Variations Plot** (Figure 3, top) shows fluctuations in the East (E), North (N), and Up (U) directions over time, likely due to multipath and measurement noise.
  - The **3D Position Plot** (Figure 3, bottom left) demonstrates the computed positions clustered around the mean position.
  - The mean position is:
    - **Latitude**: 22°19'42.3835"
    - **Longitude**: 114°10'16.9629"
    - **Height**: +5.7 m
- **Skyplot**:
  - The **Skyplot** (Figure 3, bottom right) shows the spatial distribution of the tracked satellites with a mean PDOP of 3.4446, indicating moderate geometric dilution of precision.

### **Analysis Based on Plots**
- **Figure 3 (Coordinates Variations in UTM System)**:
  - Shows the fluctuations in position computed using the WLS algorithm. Variations in the UTM coordinates demonstrate the impact of multipath and noise.
- **Figure 3 (3D Position Plot)**:
  - Visualizes the computed positions clustered around the mean position.
- **Figure 3 (Skyplot)**:
  - Displays the spatial distribution of visible satellites and the PDOP value, which reflects the satellite geometry's impact on position accuracy.

### **Discussion**
1. **Impact of Multipath**:
   - Multipath effects cause fluctuations in pseudorange measurements, leading to position errors.
   - The UTM position plot shows small deviations from the mean position, which can be attributed to multipath reflections.
2. **Comparison with Ground Truth**:
   - The computed position is close to the expected ground truth, with minor errors due to urban interference.

---

## **Summary**

### **Task 1: Acquisition**
- Successfully acquired satellites with PRN 16, 20, 27, and 31.
- **Source Plot**: Figure 2 (Acquisition Results Plot).

### **Task 2: Tracking**
- Tracking loops maintained synchronization with satellites, with sharp correlation peaks observed for Prompt correlators.
- **Source Plots**: 
  - Figure 1 (Time Domain Plot, Frequency Domain Plot, Histogram).

### **Task 3: Navigation Data Decoding**
- Ephemeris data was successfully decoded, enabling satellite position computation.
- **Source Plots**: Indirectly analyzed from Figure 3 (Coordinates Variations Plot, 3D Position Plot, Skyplot).

### **Task 4: Position and Velocity Estimation**
- The Weighted Least Squares (WLS) algorithm computed the user's position and velocity, with minor deviations caused by multipath effects.
- **Source Plots**:
  - Figure 3 (Coordinates Variations in UTM System, 3D Position in UTM System, Skyplot).

---

## **Recommendations**
1. **Multipath Mitigation**:
   - Use advanced tracking techniques to reduce the impact of multipath interference.
2. **Multi-Constellation Support**:
   - Integrate multi-GNSS data (e.g., GPS, GLONASS, Galileo) for improved satellite geometry and accuracy.
3. **Real-Time Processing**:
   - Extend the system to support real-time GNSS signal processing for dynamic applications.

---

## **Future Work**
- Implement robust filtering techniques (e.g., Kalman Filter) for improved position accuracy.
- Investigate urban interference mitigation strategies to enhance GNSS performance in challenging environments.
