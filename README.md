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
- In an open environment, the signal frequency domain is concentrated, the time domain signal is balanced, and the multi-correlator results show that the PRN signal peak is clear and the correlation is good.
- In an urban environment, the signal is interfered by the multipath effect, the noise is strong, the time domain signal fluctuates significantly, the multi-correlator result peak is low, and the signal correlation decreases.



## **Task 3: Navigation Data Decoding**

### **Objective**
Decode the navigation message and extract key parameters, such as ephemeris data, for at least one satellite.

### **Results**
Below is the navigation data message decoded from incoming signal of urban.
![image](https://github.com/ZyyFLY/AAE6102-Assignment-1-ZhangYuanyuan/blob/main/images/URBAN-PRN3.png) 
Below are the key parameters from urban message.
![image](https://github.com/ZyyFLY/AAE6102-Assignment-1-ZhangYuanyuan/blob/main/images/3-URBAN.png)  



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

### **Results**
- In an open environment, the weighted least squares method (WLS) is used to estimate the position and velocity. The results show that the position deviation is small, the velocity changes smoothly, the amplitude of the three-dimensional components is consistent, and the accuracy is high.
- In an urban environment, multipath effects and occlusions cause the position deviation to increase, the velocity estimation fluctuates violently, and the amplitude is uneven, the error increases significantly, and the algorithm performance is affected.


## **Task 5:Kalman Filter-Based Positioning**

### **Objective**
Develop an Extended Kalman Filter (EKF) using pseudorange and Doppler measurements to estimate user position and velocity.

### **1. Open-sky**
![image](https://github.com/ZyyFLY/AAE6102-Assignment-1-ZhangYuanyuan/blob/main/images/ekf-open.png)  
![image](https://github.com/ZyyFLY/AAE6102-Assignment-1-ZhangYuanyuan/blob/main/images/open-v-ekf.png)  
- 

### **2. Urban**
![image](https://github.com/ZyyFLY/AAE6102-Assignment-1-ZhangYuanyuan/blob/main/images/ekf-urban.png) 
![image](https://github.com/ZyyFLY/AAE6102-Assignment-1-ZhangYuanyuan/blob/main/images/urban-v-ekf.png) 

### **Results**
-In an open environment, the Extended Kalman Filter (EKF) algorithm performs stably on position and velocity estimation, with small position changes, moderate velocity amplitude and stable fluctuations, and can effectively track user dynamics.

-In an urban environment, due to multipath effects and occlusion, the EKF shows obvious errors, dramatic and unstable position changes, and abnormally high values ​​of velocity estimation, indicating that environmental noise has a greater impact on filter performance.
