---
layout: project
title: "💻 PROJECT #1.1"
projectname: "Moon Coding"
parent: "1️⃣ Primitive Types"
nav_order: 7
---

### Overview & Setup

🌕🌖🌑🌒🌓🌔🌕

On February 22nd, 2024, the SpaceX's **Odysseus** became the 1st American lander to reach the moon in 52 years! 

Houston-based _Intuitive Machines'_ lander is now the first commercial spacecraft to ever land on the surface of the moon, and the first American craft to do so since NASA's final Apollo mission in 1972. *[Source](https://www.usatoday.com/story/news/nation/2024/02/22/odysseus-lunar-lander-makes-history-moon-spacex-launch/72660310007/)*

<div class="setup" markdown="block">

1. Go to the `CS2 Project 1.1` assignment on **Blackbaud** and follow the provided **GitHub Classroom** link.
  > 📁 Clicking the link generates a **private repository** for your project with the appropriate starter code. Note that **projects** are stored within the [BWL-CS Organization](https://github.com/BWL-CS), so you _cannot_ access it from the "Your Repositories" page!
2. Open the repository in a **Codespace** whenever you spend time working on the program, in class or at home. 
  > ⚠️ Always remember to `commit changes` after every coding session!
3. When your project is complete, **submit the link to your repository** in the `CS2 Project 1.1` assignment on Blackbaud.

</div>

### Instructions & Requirements

<div class="task" markdown="block">

Try writing Java code to solve the problems below (based on [SpaceMath](https://spacemath.gsfc.nasa.gov/moon.html) problem 201 and 275). Make sure to use **COMMENTS** to organize your code, and watch out for **UNIT CONVERSIONS**!

#### PROBLEM #1:
**Traveling to the moon with zero gravity:** If there were no gravity, spacecraft could just travel from place to place in a straight line at their highest speeds, like the Enterprise in Star Trek. If the **distance** to the Moon is **380,000 kilometers**, and the top **speed** of a rocket to the moon is **10 kilometers/sec**, how many **hours** would it take to reach the Moon?

> **Hints:** The formula you need is `time = distance/speed`. If you’re not sure how to start, first **declare variables** for the values given in the problem, then write an **assignment statement** using the formula, and then **print** the result in hours. _Don’t forget to **convert** seconds to hours!_

#### PROBLEM #2:

**Traveling to the moon using orbits:** Since gravity makes it difficult to go in a straight line to the moon, it takes many days to get to the moon, by orbiting around the earth until rising into the moon’s orbit. To enter a Lunar Transfer Orbit, a spacecraft needs enough fuel to change its speed. If it needs to make a speed change of **2000 m/sec** in the **horizontal** direction, and **3000 m/sec** in the vertical direction to enter the correct orbit, what is the **total speed change** needed?

![image](https://lh3.googleusercontent.com/0m1x-Dcj_YXi1kWBeZNRBQJ5dhR6YjxxGKy0yZV5yHUskrp2TDqYeaV3rNh8duvWd4VHd6wiPBRC5iuJZZcXhX7-WmwzZc4P-5ZXAH7mCkodnTpmPic)

> **Hint:** In Physics you'll learn that you need to use the _Pythagorean Theorem_ to calculate total speed from its horizontal and vertical components. From the lengths of the horizontal speed (`a` is `2000`) and vertical speed (`b` is `3000`), we want to solve for `c`, the **total speed change** needed to get to the correct orbit. You'll need to use the Java function `Math.sqrt()` to get the **square root** of a number.

```java
double x = 9;
double result = Math.sqrt(x); // result = 3
```                       

#### PROBLEM #3:

**Water on the Moon:** On August 23, 2023, the _Chandrayaan-3_ spacecraft launched from India was the first ever landing on the moon’s south pole! One of Chandrayaan 3’s missions is to look for water on the south pole of the moon. The Chandrayaan 1 mission measured hydroxyl molecules (which are 1 oxygen and 1 hydrogen, -OH, close to the H20 molecule for water) on 25% of the moon’s surface! Water can be harvested for life and fuel.

  a. The **radius** of the moon is 1731 kilometers (first multiply this by 1000 to get radius in meters). How many **cubic meters of surface volume** is present in a layer that is 1 millimeter thick?      
  > **Hints:** For a sphere, `surface area = 4 * π * r^2` where you can approximate 3.14 for π. To be extra precise, use the Java property `Math.PI` in place of 3.14. The **volume** of the surface layer is the surface **area** multiplied by the **thickness** (note that `1mm = 0.001m`).

  b. The **density** of the lunar surface (called the _regolith_) is about 3000 kilograms/meter^3. How many **metric tons of regolith** are found in the surface volume calculated in problem (a) above? 
  > **Hints:** `density = mass / volume`. The result of problem (a) gives you the VOLUME. You are solving for MASS. After, you'll need to convert to metric tons (note that `1 metric ton = 1000 kilograms`).

  c. How many **liters** of water could be recovered from the 1 millimeter thick surface layer if 25% of the lunar surface contains water? 
  > **Hints:** Liters are a unit of VOLUME, which you calculated in problem (a). Find 25% of that volume, then, convert it into liters (note that `1 cubic meter = 1000 liters`). 

</div> 

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from []().
{: .fs-2 }
