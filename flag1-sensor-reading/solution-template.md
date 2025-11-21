# Flag 1 Solution: Sensor Reading
# Flag 1 解决方案：传感器读取

**Student Name | 学生姓名**: Bo Chen

**Date Completed | 完成日期**: 11.21.2025

---

## 📋 Sensor Information | 传感器信息

### Which sensor did you choose? | 你选择了哪个传感器？

**Sensor Name | 传感器名称**: Temperature Sensor LM35

**Sensor Type | 传感器类型**: ☐ Analog (模拟)

---

### What does this sensor measure? | 这个传感器测量什么？

*Describe what the sensor detects or measures*  
*描述传感器检测或测量什么*
Temperature



---

## 🔌 Wiring | 接线

### Pin Connections | 引脚连接

Fill in how you connected your sensor:

填写你如何连接传感器：

Sensor VCC  →  Arduino 5V
Sensor GND  →  Arduino GND
Sensor OUT  →  Arduino Analog Pin (e.g., A0)

**Additional components used | 使用的额外组件**:

- [ ] None / No additional components

---

### Wiring Photo | 接线照片

*Optional but recommended! Upload a photo and link it here.*  
*可选但推荐！上传照片并在此链接。*

![Wiring Photo](./wiring.jpg)

*Or describe your wiring setup in words:*  
*或用文字描述你的接线设置：*
A temperature sensor is wired to a buzzer.



---

## 💻 Code | 代码

### Complete Arduino Code | 完整Arduino代码

*Paste your complete, working code here. Make sure it's properly commented!*  
*在此粘贴你完整的、能工作的代码。确保有适当的注释！*

```cpp
// Paste your code here
// 在此粘贴代码

// Project – Temperature Alarm  
float sinVal;            // Variable to store sine function value  
int toneVal;             // Variable to store tone frequency  
unsigned long tepTimer;  // Timer for periodic temperature output  
  
void setup(){   
    pinMode(8, OUTPUT);  // Set pin 8 as OUTPUT for buzzer  
    Serial.begin(9600);  // Start serial communication at 9600 bps  
}  
  
void loop(){   
    int val;          // Variable to store the value read from LM35  
double data;  
// Variable to store the converted temperature value  
val = analogRead(0);   
// Read the value from analog pin 0 connected to LM35  
data = (double) val * (5.0/10.24);  
// Convert voltage to temperature  
       
if(data > 27){        
// If the temperature is greater than 27, sound the buzzer  
          for(int x = 0; x < 180; x++){  
            // Convert angle for sine function to radians  
            sinVal = (sin(x * (3.1412/180)));  
            // Generate tone frequency using sine function value  
            toneVal = 2000 + (int(sinVal * 1000));  
            // Play tone on pin 8  
            tone(8, toneVal);  
            delay(2);   
     }     
} else {    
// If the temperature is less than 27, stop the buzzer  
           noTone(8);          // Stop the buzzer  
    }  
       
if(millis() - tepTimer > 500){     
// Every 500ms, print temperature to serial port  
             tepTimer = millis();  
             Serial.print("temperature: ");     
// Print "temperature" to serial port  
             Serial.print(data);               
// Print temperature value to serial port  
             Serial.println("C");              
// Print temperature unit to serial port  
       }   
}





```

---

### Code Explanation | 代码解释

**What does your code do? Explain the main parts:**  
**你的代码做什么？解释主要部分：**

**Setup Section | 设置部分**:

Measures temperature.


**Loop Section | 循环部分**:

Reads the analog value from LM35 and converts it into a temperature.

Every 500 ms, prints the current temperature to the Serial Monitor.


**Key Functions Used | 使用的关键函数**:

- [ ] `analogRead()`
- [ ] `Serial.begin()`
- [ ] `Serial.print()` / `Serial.println()`


---

## 📊 Test Results | 测试结果

### Serial Monitor Output | 串口监视器输出

*Take a screenshot of your Serial Monitor showing sensor readings*  
*截取显示传感器读数的串口监视器截图*

![TEM-35](image.png)

---

### Observed Behavior | 观察到的行为

**What happened when you tested your sensor?**  
**测试传感器时发生了什么？**
There were reads of temperature



**What range of values did you see?**  
**你看到的值范围是多少？**

Minimum value | 最小值: 24.90C  
Maximum value | 最大值: 25.39C
---

### Testing Process | 测试过程

**How did you test your sensor?**  
**你如何测试传感器？**

Didn't do much stuff.




---

## 🎓 Reflection | 反思

### What Worked Well | 什么做得好

The connection.


---

### Challenges Faced | 面临的挑战

**Did you encounter any problems? How did you solve them?**  
**遇到任何问题了吗？你如何解决的？**
The wiring was opposite.
I rewired it.


---

### What I Learned | 我学到的东西

**What new things did you learn from this challenge?**  
**从这个挑战中你学到了什么新东西？**
Wiring using arduino.



---

### How Long Did This Take? | 这花了多长时间？

**Estimated time spent | 估计花费时间**: 10 minutes (分钟)

---

## ✅ Verification | 验证

Check off these items before submitting:

提交前勾选这些项目：

- [ ] Code compiles without errors (代码编译无错误)
- [ ] Serial Monitor shows sensor readings (串口监视器显示传感器读数)
- [ ] Sensor responds to changes (传感器对变化有响应)
- [ ] Code is commented and clean (代码有注释且整洁)
- [ ] All sections of this template are filled out (模板的所有部分都已填写)
- [ ] Photo or detailed wiring description included (包含照片或详细接线描述)

---

## 🚀 Next Steps | 下一步

**Are you ready to move to Flag 2?**  
**准备进入Flag 2了吗？**

☐ Yes, let's go! (是的，走吧！)  


---

## 🎉 Congratulations! | 恭喜！

**You've captured Flag 1!** 🚩  
**你捕获了Flag 1！** 🚩

You now understand how to:
- Connect sensors to Arduino (将传感器连接到Arduino)
- Read sensor data (读取传感器数据)
- Use Serial Monitor for debugging (使用串口监视器调试)

**Keep going - Flag 2 awaits!** 🚀  
**继续前进 - Flag 2 等着你！** 🚀

---

**Date Submitted | 提交日期**: 11.21.2025

**Instructor Feedback | 讲师反馈**:

