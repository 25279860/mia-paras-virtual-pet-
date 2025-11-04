# mia-paras-virtual-pet-
my virtual pet assignment 
https://makecode.microbit.org/_gMiUk7CHthvV

# Micro:bit Virtual Pet Game  

**Author:** [Mia Paras]  
**Date:** [4/11/25]  

---

## Project Overview  
This project is a **virtual pet game** developed for the **BBC Micro:bit**, designed to simulate caring for a small digital creature. The player interacts with the pet through button presses and motion gestures — feeding, resting, and shaking — each of which affects the pet’s overall **health**, **happiness**, and **hunger**.

The goal of this prototype is to demonstrate **code literacy** by building an **event-driven, interactive system** using Micro:bit’s input sensors, LED matrix, and sound outputs. The game also reflects key programming principles such as **variables**, **loops**, **conditionals**, and **functions**.



# Core Features  

- **Button A → Feeding:** Increases health by +1.  
- **Shake Gesture → Activity:** Decreases health by -2 to simulate tiredness or overexertion.  
- **Screen-Up Gesture → Sleep Mode:** Restores health gradually over time.  
- **Health Display:** Shows different facial icons depending on health values.  
- **Death Condition:** When health ≤ 0, a skull icon appears and a funeral melody plays.  
- **Continuous Game Loop:** `basic.forever()` maintains the pet’s life cycle, ensuring constant interaction and feedback.



# Code Concepts Demonstrated

| Concept | Description |
|----------|--------------|
| **Event-Driven Programming** | Code responds to user input like button presses and gestures (`input.on_button_pressed`, `input.on_gesture`). |
| **Global Variables** | Shared variables (`health`, `happiness`) track changing states of the pet. |
| **Conditional Statements** | Used to determine emotional states and display icons (`if health > 6`, etc.). |
| **Iteration & Timing** | `basic.forever()` loop and `basic.pause(2500)` manage time-based health reduction. |
| **Debugging & Testing** | Adjusted timing (from 1000 ms to 2500 ms) to prevent the pet from dying too quickly. |
| **Creative Design** | Icons and sounds create emotional feedback, encouraging player empathy. |

---

# How to Run the Code  

1. Open the [Micro:bit MakeCode Editor](https://makecode.microbit.org/) or your Python IDE.  
2. Copy and paste the code from `virtual_pet.py` into the editor.  
3. Download the `.hex` file and flash it to your Micro:bit using USB.  
4. Interact with the pet:  
   - Press Button A to feed it.  
   - Shake the Micro:bit to stress it.  
   - Turn the screen-up to let it sleep and recover.  
5. Watch the LED display change faces and hear different sounds based on your actions.  



 # Example Code Snippet  

```python
def on_button_pressed_a():
    global health
    health += 1
input.on_button_pressed(Button.A, on_button_pressed_a)

def on_gesture_shake():
    global health
    health += -2
input.on_gesture(Gesture.SHAKE, on_gesture_shake)

def on_forever():
    global health
    if health > 0:
        basic.pause(2500)
        health += -1
basic.forever(on_forever)
