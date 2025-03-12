# GNSS SDR Signal Processing and Analysis

## **Task 1: Acquisition**

### **Objective**
Process the IF data using a GNSS SDR to identify visible satellites and generate the initial acquisition results.

### **1. Open-sky**
![image](https://github.com/ZyyFLY/AAE6102-Assignment-1-ZhangYuanyuan/blob/main/images/1-open.png)  
- The **Acquisition Results Plot** shows that satellites with PRN 16, 22,26, 27 and 31 are successfully acquired with high acquisition metrics.

### **2. Urban**
![image](https://github.com/ZyyFLY/AAE6102-Assignment-1-ZhangYuanyuan/blob/main/images/1-urban.png)
- The **Acquisition Results Plot** shows that satellites with PRN 1,3,11 and 18 are successfully acquired with high acquisition metrics.


## **Task 2: Tracking**

### **Objective**
Adapt the tracking loop (DLL) to generate correlation plots and analyze tracking performance. Discuss the impact of urban interference on correlation peaks.

### **1. Open-sky**
![image](https://github.com/ZyyFLY/AAE6102-Assignment-1-ZhangYuanyuan/blob/main/images/2-open1.png)  
![image](https://github.com/ZyyFLY/AAE6102-Assignment-1-ZhangYuanyuan/blob/main/images/open-ACF.png)  
- 

### **2. Urban**
![image](https://github.com/ZyyFLY/AAE6102-Assignment-1-ZhangYuanyuan/blob/main/images/2-urban.png) 
![image](https://github.com/ZyyFLY/AAE6102-Assignment-1-ZhangYuanyuan/blob/main/images/urban-ACF.png)  


### **Results**
- **Correlation Peaks**:
  - The tracking loop maintained synchronization with the acquired satellites.
  - The correlation peaks for Prompt correlators were sharp, indicating successful tracking.
- **Impact of Urban Interference**:
  - Urban environments introduce interference that may degrade the correlation peaks, causing them to flatten or shift.
  - Multipath effects can lead to secondary peaks, potentially affecting code phase estimation.

### **Analysis Based on Plots**

## **Task 3: Navigation Data Decoding**

### **Objective**
Decode the navigation message and extract key parameters, such as ephemeris data, for at least one satellite.

### **Results**
![image](https://github.com/ZyyFLY/AAE6102-Assignment-1-ZhangYuanyuan/blob/main/images/URBAN-PRN3.png) 
![image](https://github.com/ZyyFLY/AAE6102-Assignment-1-ZhangYuanyuan/blob/main/images/3-URBAN.png)  

### **Analysis Based on Plots**
- **Navigation Results Derived from Tracking Data**:


## **Task 4: Position and Velocity Estimation**

### **Objective**
Using pseudorange measurements from tracking, implement the Weighted Least Squares (WLS) algorithm to compute the user's position and velocity.

### **1. Open-sky**
![image](https://github.com/ZyyFLY/AAE6102-Assignment-1-ZhangYuanyuan/blob/main/images/wls-open.png)  
![image](https://github.com/ZyyFLY/AAE6102-Assignment-1-ZhangYuanyuan/blob/main/images/open-v.png)  
- 

### **2. Urban**
![image](https://github.com/ZyyFLY/AAE6102-Assignment-1-ZhangYuanyuan/blob/main/images/wls-urban.png) 
![image](https://github.com/ZyyFLY/AAE6102-Assignment-1-ZhangYuanyuan/blob/main/images/urban-v.png)  

### **Analysis Based on Plots**


## **Task 5:Kalman Filter-Based Positioning**

### **Objective**
Develop an Extended Kalman Filter (EKF) using pseudorange and Doppler measurements to estimate user position and velocity.

### **1. Open-sky**
![image](https://github.com/ZyyFLY/AAE6102-Assignment-1-ZhangYuanyuan/blob/main/images/ekf-open.png)  
![image](https://github.com/ZyyFLY/AAE6102-Assignment-1-ZhangYuanyuan/blob/main/images/open-v-ekf.png)  
- 

### **2. Urban**
![image](https://github.com/ZyyFLY/AAE6102-Assignment-1-ZhangYuanyuan/blob/main/images/ekf-urban.png) 


### **Analysis Based on Plots**
