# 英文推理能力快速测试

本测试是给那些中文训练语料太少导致模型无法精准理解中文的模型快速测试其对英文问题的推理能力。来自一部分中文测试题的翻译。

评分标准：两次尝试内有一次正确：5分；两次还做不到：0分。

### 塔台高度

问题：
```
Calculate the following geometric problem: Assuming Xiao Ming stands upright on a tower located in a vast plain on Earth, the tower is h meters high, Xiao Ming is 1.7 meters tall, and his eyes are 10 cm below the top of his head. Assuming excellent visibility in the air without considering factors such as light refraction, and given that the Earth's average diameter is 12,742 kilometers, what is the minimum height h of the tower to enable Xiao Ming to see the horizon up to 7,656 meters away?
```

正确答案：`3米`

### 概率统计

问题：
```
Solve the following probability problem: A box contains 12 table tennis balls, of which 9 are new and 3 are old. Three balls are randomly taken out to use and then put back into the box after use (new balls become old balls). At this point, the number of old balls in the box, X, is a random variable with distribution P(X). What is the value of P(X=4)? Express the result as a fraction.
```
正确答案：27/220（小数大约是0.12272727...）

### 赌徒输赢

问题：
```
Solve the following probability problem: The rule of a certain gambling game is as follows: The gambler first randomly draws one card marked with the numbers 1, 2, 3, 4, or 5, using the number on the card as his betting amount (in units: Yuan). Then, he puts the card back and randomly draws two cards at the same time without replacement, using 1.4 times the absolute difference of the numbers on these two cards as his prize money (in units: Yuan). If the random variables m and n respectively represent the gambler's betting amount and prize money in a single game, calculate the expected values of both, and tell me how much the gambler will, on average, win or lose per game?
```
正确答案：赌金m的数学期望：3元；奖金n的数学期望：2.8元；赌客平均每局输去0.2元。

### 水库水量

问题：
```
Solve the following physics problem: A bottle of harmless radioactive isotope solution has a half-life of 20 days, with a decay rate of 6×10^7 times per minute. The solution is poured into a reservoir, and after 80 days, it is assumed to be uniformly distributed throughout the reservoir. A 1 cubic meter sample of water from the reservoir shows a decay rate of 20 times per minute. What is the volume of water in the reservoir in cubic meters?
```
正确答案：`187,500 立方米（1.875×10^5立方米）`

### 行星半径

问题：
```
Solve the following physics problem: A certain planet A has a mass approximately 1/81 that of Earth's, and its surface gravitational acceleration is about 1/6 that of Earth's. If the Earth's radius is R, what is the radius of planet A? (Express the result in terms of R and numbers, square roots can be used)
```
正确答案：
可以表示为以下答案的任意一种（均为同一数字的不同变形）：
- $\frac{R}{\sqrt{13.5}}$
- $0.2722R$
- $\frac{\sqrt{6} \cdot R}{9}$


### 溶液pH

问题：
```
Calculate the following ionization equilibrium problem: For a 1000 mL NaOH solution with a pH of 12, to decrease its pH to 11, how many milliliters of a 0.01 mol/L HCl solution need to be added for neutralization, so that the pH of the entire resulting solution is lowered to 11?
```
正确答案：818.1818181...毫升（约818.2毫升）


### 谁的女儿

问题：
```
Xiaohong is the only daughter in the family. Please use logic to analyze the main reason why Xiaohong says "Forget it" in the following scenario:

Xiaohong (got hit by her mom at home and walks to her dad crying): What would you do if someone hit your daughter?
Dad: If anyone dares to hit my daughter, I will hit their daughter.
Xiaohong (turns around and walks away, crying even harder): Then forget it.
```

期望回答：意识到如果按照爸爸的逻辑行事，他会因为妈妈打小红而再次去打小红，**小红会再被打一次**。（只要回答中有该要点即可）



### 新家庭关系

问题：
```
Please answer the following logic question:

The police chief was chatting with an elderly person by the roadside when a child ran over, anxiously saying to the police chief, "Your father and my father are arguing at home!"
The elderly person asked, "Who is this child to you?"
The police chief replied, "He is my son."
Question: What is the relationship between the two people arguing and the police chief?
```

期望回答：
这里的关键是不要把小孩说的"我爸爸"认为是正在路边和老人聊天的警察局长。
```
两个吵架的人分别是警察局长的丈夫(男性配偶)和父亲。
```
