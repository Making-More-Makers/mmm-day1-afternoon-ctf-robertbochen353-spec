# Flag 2 Solution: Actuator Control
# Flag 2 解决方案：执行器控制

**Student Name | 学生姓名**: Bo Chen

**Date Completed | 完成日期**: 11.21.2025

---

## 📋 Actuator Information | 执行器信息

### Which actuator did you choose? | 你选择了哪个执行器？

**Actuator Name | 执行器名称**: 

**Actuator Type | 执行器类型**: 

- [ ] Buzzer (蜂鸣器)
- 

---

### What does this actuator do? | 这个执行器做什么？

*Describe what the actuator controls or produces*  
*描述执行器控制或产生什么*

Produces a melody in "Mia & Seb's Theme"


---

## 🔌 Wiring | 接线

### Pin Connections | 引脚连接

Fill in how you connected your actuator:

填写你如何连接执行器：

| Actuator Pin | Arduino Pin | Connection Type | 执行器引脚     | Arduino引脚 | 连接类型 |
| ------------ | ----------- | --------------- | --------- | --------- | ---- |
| Buzzer +     | D8          | Digital         | 蜂鸣器正极 (+) | D8        | 数字信号 |
| Buzzer –     | GND         | Ground          | 蜂鸣器负极 (–) | GND       | 接地   |


**Additional components used | 使用的额外组件**:


---

### Wiring Photo | 接线照片

*Upload a photo and link it here*  
*上传照片并在此链接*

![Wiring Photo](./wiring.jpg)

*Or describe your wiring setup:*  
*或描述你的接线设置：*




---

## 💻 Code | 代码

### Complete Arduino Code | 完整Arduino代码

*Paste your complete, working code here with comments!*  
*在此粘贴你完整的、能工作的代码并加注释！*

```cpp
// Paste your code here
// 在此粘贴代码
//Project - Melody Buzzer
#define NOTE_B0  31
#define NOTE_C1  33
#define NOTE_CS1 35
#define NOTE_D1  37
#define NOTE_DS1 39
#define NOTE_E1  41
#define NOTE_F1  44
#define NOTE_FS1 46
#define NOTE_G1  49
#define NOTE_GS1 52
#define NOTE_A1  55
#define NOTE_AS1 58
#define NOTE_B1  62
#define NOTE_C2  65
#define NOTE_CS2 69
#define NOTE_D2  73
#define NOTE_DS2 78
#define NOTE_E2  82
#define NOTE_F2  87
#define NOTE_FS2 93
#define NOTE_G2  98
#define NOTE_GS2 104
#define NOTE_A2  110
#define NOTE_AS2 117
#define NOTE_B2  123
#define NOTE_C3  131
#define NOTE_CS3 139
#define NOTE_D3  147
#define NOTE_DS3 156
#define NOTE_E3  165
#define NOTE_F3  175
#define NOTE_FS3 185
#define NOTE_G3  196
#define NOTE_GS3 208
#define NOTE_A3  220
#define NOTE_AS3 233
#define NOTE_B3  247
#define NOTE_C4  262
#define NOTE_CS4 277
#define NOTE_D4  294
#define NOTE_DS4 311
#define NOTE_E4  330
#define NOTE_F4  349
#define NOTE_FS4 370
#define NOTE_G4  392
#define NOTE_GS4 415
#define NOTE_A4  440
#define NOTE_AS4 466
#define NOTE_B4  494
#define NOTE_C5  523
#define NOTE_CS5 554
#define NOTE_D5  587
#define NOTE_DS5 622
#define NOTE_E5  659
#define NOTE_F5  698
#define NOTE_FS5 740
#define NOTE_G5  784
#define NOTE_GS5 831
#define NOTE_A5  880
#define NOTE_AS5 932
#define NOTE_B5  988
#define NOTE_C6  1047
#define NOTE_CS6 1109
#define NOTE_D6  1175
#define NOTE_DS6 1245
#define NOTE_E6  1319
#define NOTE_F6  1397
#define NOTE_FS6 1480
#define NOTE_G6  1568
#define NOTE_GS6 1661
#define NOTE_A6  1760
#define NOTE_AS6 1865
#define NOTE_B6  1976
#define NOTE_C7  2093
#define NOTE_CS7 2217
#define NOTE_D7  2349
#define NOTE_DS7 2489
#define NOTE_E7  2637
#define NOTE_F7  2794
#define NOTE_FS7 2960
#define NOTE_G7  3136
#define NOTE_GS7 3322
#define NOTE_A7  3520
#define NOTE_AS7 3729
#define NOTE_B7  3951
#define NOTE_C8  4186
#define NOTE_CS8 4435
#define NOTE_D8  4699
#define NOTE_DS8 4978
int melody[] = {
  NOTE_CS4, NOTE_FS4, NOTE_GS4, NOTE_A4, NOTE_GS4, NOTE_FS4, NOTE_D4
};  //sequence of notes in the melody
 
int noteTypes[] = {
  4, 4, 4, 4, 4, 4, 4, 2
};  //type of each note: 4 = quarter note, 8 = eighth note
 
void setup() {
 
  for (int thisNote = 0; thisNote < 8; thisNote++) {
int noteDuration = 1000 / noteTypes[thisNote]; 	
//calculate the note duration: 1 second / note type
tone(8, melody[thisNote], noteDuration); 
//play the note on pin 8
    int pauseBetweenNotes = noteDuration * 1.30;  /*calculate the pause time according to the note duration to make the melody sound more natural*/
    delay(pauseBetweenNotes);  //pause between the notes
    noTone(8);  //stop the tone playing on pin 8
  }
}
 
void loop() {
  // no need to repeat the melody
}





```

---

### Code Explanation | 代码解释

**Describe your control logic:**  
**描述你的控制逻辑：**

**Setup Section | 设置部分**:

Defines an array of musical notes (melody[]) and their corresponding durations (noteTypes[]).

In setup(), loops through each note:

Calculates the note duration based on musical type (e.g., quarter note).

Uses tone() to play the note on pin 8.

Adds a pause between notes for natural rhythm.

Stops the tone with noTone() before moving to the next note.


**Loop Section | 循环部分**:
Empty, because the melody only plays once when the Arduino starts.

No repeated actions occur in the loop.



**Control Method Used | 使用的控制方法**:

- [ ] `tone()` / `noTone()` - Sound frequency

---

## 🎯 Behaviors Demonstrated | 演示的行为

### Behavior 1 | 行为1

**Description | 描述**:




**Parameters | 参数**:
- Delay/Timing: _______ms
- Value/Position: _______
- Other settings: _______

---

### Behavior 2 | 行为2

**Description | 描述**:
Plays each musical note in the melody sequence using the buzzer, producing a rising–falling tune. Each note has a fixed musical duration (quarter note), followed by a short pause to create rhythm.



**Parameters | 参数**:
Delay/Timing: ~noteDuration × 1.30 (约 300–350ms per note)

Value/Position: melody[] notes (e.g., NOTE_CS4, NOTE_FS4…)

Other settings: tone(8, frequency, duration) + noTone(8)

---

### Additional Behaviors (Optional) | 额外行为（可选）

**Behavior 3+**:




---

## 📸 Demonstration | 演示

### Photo/Video | 照片/视频

*Upload a photo or video showing your actuator in action*  
*上传显示执行器运行的照片或视频*

![Demo Photo/Video](./demo.jpg)

---

### Observed Behavior | 观察到的行为

**What happened when you ran your code?**  
**运行代码时发生了什么？**
A pre-designed melody was played.



**Did it work as expected?**  
**按预期工作了吗？**

☐ Yes, perfectly! (是的，完美！)  


---

## 🎓 Reflection | 反思

### What Worked Well | 什么做得好
The wiring and music design



---

### Challenges Faced | 面临的挑战

**Did you encounter any problems? How did you solve them?**  
**遇到任何问题了吗？你如何解决的？**

Not really


---

### What I Learned | 我学到的东西

**What new concepts did you learn?**  
**你学到了什么新概念？**
Music can be played with a buzzer



**Key functions or techniques:**  
**关键函数或技术：**
How to show notes with codes.



---

### Creative Additions (Bonus) | 创意添加（加分）

**Did you add any extra features or patterns?**  
**你添加了任何额外功能或模式吗？**




---

## 🔄 Comparison with Flag 1 | 与Flag 1的比较

**How is controlling an actuator different from reading a sensor?**  
**控制执行器与读取传感器有何不同？**

| Aspect         | Sensor (Flag 1)                 | Actuator (Flag 2)                           | 方面   |
| -------------- | ------------------------------- | ------------------------------------------- | ---- |
| Direction      | Input                           | Output                                      | 方向   |
| Function       | Read data from environment      | Send commands to make device act            | 功能   |
| Pin Mode       | `INPUT`                         | `OUTPUT`                                    | 引脚模式 |
| Main Functions | `digitalRead()`, `analogRead()` | `digitalWrite()`, `analogWrite()`, `tone()` | 主要函数 |


---

## ⏱️ Time Spent | 花费时间

**Estimated time spent | 估计花费时间**: 20 minutes (分钟)

**Breakdown | 分解**:
- Wiring: 8min (接线)
- Coding: 2min (编码)
- Testing/Debugging: 8min (测试/调试)
- Documentation: 2min (文档)

---

## ✅ Verification | 验证

Check off these items before submitting:

提交前勾选这些项目：

- [ ] Code compiles without errors (代码编译无错误)
- [ ] Actuator responds correctly to code (执行器正确响应代码)
- [ ] At least 2 different behaviors demonstrated (演示了至少2种不同行为)
- [ ] Code is well-commented (代码有良好注释)
- [ ] All sections of this template filled out (模板的所有部分都已填写)
- [ ] Photo or video of working demo included (包含工作演示的照片或视频)

---

## 🚀 Next Steps | 下一步

**Reflections for Flag 3:**  
**Flag 3的思考：**

In Flag 3, you'll combine sensors and actuators. Based on what you learned:

在Flag 3中，你将结合传感器和执行器。基于你学到的：

**What sensor-actuator combination would you like to try?**  
**你想尝试什么传感器-执行器组合？**

Examples:

- temperature sensor → Buzzer (光线传感器 → 蜂鸣器)


**Your idea | 你的想法**:




---

## 🎉 Congratulations! | 恭喜！

**You've captured Flag 2!** 🚩  
**你捕获了Flag 2！** 🚩

You now understand how to:
- Control output devices (控制输出设备)
- Use digital and PWM signals (使用数字和PWM信号)
- Create patterns and behaviors (创建模式和行为)
- Time events with delays (用延迟计时事件)

**Ready for the next challenge? Let's connect sensors to actuators!** 🚀  
**准备好下一个挑战了吗？让我们将传感器连接到执行器！** 🚀

---

**Date Submitted | 提交日期**: _________________

**Instructor Feedback | 讲师反馈**:

