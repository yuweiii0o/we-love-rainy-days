# we-love-rainy-days

## **1. Project Overview**

*We Love Rainy Days* is an interactive, networked audio-visual project built with p5.js and WebSocket. The visual environment simulates a rainy atmosphere using falling line particles, while each user is represented as a moving raindrop.

When two raindrops collide, a ripple effect appears at the point of contact, and a soft musical chord is triggered. The project explores how simple interactions between users can create shared visual and sonic experiences in real time.

---

## **2. Concept**

The project is inspired by the poetic and emotional qualities of rainy days. Rain is often associated with calmness, reflection, and subtle connections between elements.

In this work:

* The **rain** represents the environment and atmosphere
* The **raindrops (users)** represent individuals moving within a shared space
* The **collisions** represent moments of encounter and connection
* The **ripples and sound** represent the impact of these interactions

Instead of direct communication, users connect through **movement, proximity, and sound**, forming an indirect but shared experience.

---

## **3. Interaction Design**

* Each user controls a raindrop using the mouse
* Multiple users are connected in real time through WebSocket
* When two users come close:

  * A **collision is detected**
  * A **ripple animation** expands outward
  * A **chord is played using p5.PolySynth**
  * Both users briefly glow to indicate interaction

This creates a system where users can **“play together”** without explicit instructions.

---

## **4. Technical Implementation**

### **WebSocket (Real-time Communication)**

* The project uses WebSocket (via Socket.IO) to:

  * Track all connected users
  * Synchronize positions in real time
  * Broadcast collision events

Each client:

* Sends its position (`mouseX`, `mouseY`)
* Receives all players’ positions
* Responds to collision messages

### **Collision Detection**

* Distance between every pair of players is calculated
* When distance < threshold:

  * Collision is triggered
  * A cooldown prevents repeated triggering

### **Audio**

* Uses p5.sound and PolySynth
* Requires user interaction (`userStartAudio()`) to unlock playback

---

## **5. Future Development**

Possible improvements include:

* Adding spatialized audio (distance-based sound)
* More complex ripple physics
* Different weather modes (wind, storm, fog)
* Recording and replaying interaction patterns

---

## **6. Conclusion**

*We Love Rainy Days* explores how simple rules and real-time interaction can create a shared poetic experience. By combining rain visuals, sound, and networked interaction, the project turns small encounters into meaningful moments.
