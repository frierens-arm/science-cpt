# Science CPT Speaker Script — Microclimate Monitoring

> **Style**: Confident, conversational, Steve Jobs energy.
> **Tip**: Don't read the slides. The slides are visuals. YOU tell the story.
> **Total time**: ~8-10 minutes

---

## Slide 1 — Title
*"Microclimate Monitoring"*

**Script:**
> "What if I told you that the air five steps to your left — right now — might have completely different temperature and humidity than where you're standing?"

**Alternatively, if that feels too dramatic:**
> "I'm going to talk about something we all experience but never actually measure — the tiny climate zones all around us. I built a system to measure them."

**Say your name + course code.**

**Pause. Let them look at the slide. Move on.**

---

## Slide 2 — The Question
*"We experience different feelings in different places. But how different are they, really?"*

**Script:**
> "We've all walked outside near a lake and felt that cool, damp air. Or stood near a running computer and felt the heat coming off it. We *feel* the difference. But here's the thing — nobody in this room can tell me the *actual* numbers. How many degrees different is it? How much more humid?"

> "I wanted to find out. With real data."

**Speaker note:** This is your "hook." Lean into it. Make it personal.

---

## Slide 3 — Hypothesis
*"If a BME280 sensor is placed in three different microenvironments..."*

**Script:**
> "Before I collected any data, I made a prediction. This is my hypothesis."

> "I predicted that places near water would show higher humidity, and places near electronics would show higher temperature — compared to a neutral indoor spot."

> "The reason is pretty straightforward: water evaporates into the air around a pond, raising humidity. Electronics convert electrical energy into heat. Both of these are things we know — but I wanted to *measure* how much of a difference they actually make."

---

## Slide 4 — Research Question
*"How do temperature and humidity readings vary across three different microenvironments?"*

**Script:**
> "Here's my research question. It's specific and testable:"

> "How do temperature and humidity vary across three locations — outdoor near water, indoor near electronics, and a neutral indoor spot — all sampled for five minutes each?"

> "Three locations. Five minutes each. Temperature and humidity. Keeping everything else the same so the only variable is *where* the sensor is."

**Speaker note:** Point to the big numbers at the bottom of the slide when you say "three," "five," "two."

---

## Slide 5 — Variables

**Script:**
> "In any experiment, you need to be clear about your variables — what changes, what you measure, and what stays the same."

> "My *independent variable* — the thing I deliberately changed — was the location. Pond edge, homelab, and a hallway as my control."

> "My *dependent variables* — what I measured — were temperature in Celsius and relative humidity in percent."

> "And the *controlled variables* — the things I kept the same — were the sensor, the Pi, the five-minute duration, the ten-second sampling interval, and the time of day. Everything stays constant except location."

**Speaker note:** Point to each row on the slide as you explain. This section shows *Thinking* marks on the rubric — it shows you understand experimental design.

---

## Slide 6 — Equipment

**Script:**
> "Here's what I used. Pretty simple setup."

> "A Raspberry Pi 5 — that's a small, affordable computer. Connected to a BME280 sensor, which is a digital sensor that reads temperature, humidity, and air pressure over I2C — that's a communication protocol for hardware."

> "Breadboard and jumper wires to connect them. A power bank so I can take it outside. And a laptop to SSH into the Pi remotely and start the script."

> "The beauty of this is it's all under $50 in parts."

---

## Slide 7 — The Three Locations

**Script:**
> "Let me walk you through the three spots I tested."

> "First: at the edge of a pond. Outdoor, shaded, near standing water. I expected higher humidity here because of evaporation."

> "Second: my homelab. That's where I keep my servers and networking gear — all running, generating heat. I expected the highest temperature here."

> "Third: a hallway indoors. No strong heat sources, no moisture. This is my *control* — the baseline to compare the other two against."

**Speaker note:** This is where you show *Knowledge* marks — you understand WHY each location behaves differently.

---

## Slide 8 — Method

**Script:**
> "The procedure is simple and repeatable."

> "Wire the sensor to the Pi. Write the Python script. Then visit each location, place the sensor down, start the script, wait five minutes, and move to the next one."

> "The script logs a reading every ten seconds. That's 30 readings per location. Same Pi, same sensor, same script — only the location changes."

> "That's what makes this a fair test."

**Speaker note:** Emphasize the fairness. Teachers love hearing "fair test" and "controlled variables."

---

## Slide 9 — The Code
*"~20 lines. Simple. Clean. Does one thing well."*

**Script:**
> "Here's the code. And honestly, it's beautiful in its simplicity — about 20 lines."

> "It imports the sensor library, sets up I2C communication, and then runs a loop: read the sensor, write to a CSV file, wait 10 seconds, repeat. After 5 minutes, it saves the file and stops."

> "One thing I want to point out — the LOCATION variable is just a string. I change it before each run, and it names the output CSV file. That way I know exactly which data belongs to which location."

**Speaker note:** If your teacher asks about the code, you can scroll through the slide and explain line by line.

---

## Slide 10 — Expected Results

**Script:**
> "Now, I haven't collected my final data yet — so let me show you what I *expect* to see based on the science."

> "The pond edge should read around 18 degrees with humidity above 70% — the evaporating water pushes moisture into the air."

> "The homelab should be the warmest — maybe around 26 degrees — with lower humidity around 35%. Electronics generate heat and warm air holds moisture differently."

> "And the hallway, my control, should sit in the middle — around 21 degrees and 50% humidity."

> "Once I have the actual data, I'll replace these numbers with real readings."

**Speaker note:** Being honest about expected vs. actual results shows scientific integrity. Teachers respect this.

---

## Slide 11 — Why It Matters
*"Microclimates affect comfort, energy use, and even hardware lifespan."*

**Script:**
> "So why does any of this matter? It's not just a school project."

> "Server rooms overheat. That costs companies millions in cooling. Plants die when humidity is wrong. People get sick in poorly ventilated spaces."

> "Understanding microclimates with real data helps us make better decisions — about where to put computers, how to ventilate a building, or even where to plant a garden."

> "Data over assumptions."

---

## Slide 12 — Closing
*"Data Over Assumptions"*

**Script:**
> "That's really what this project is about. We make assumptions about our environment every day — 'it feels warmer in here' or 'it's more humid outside.' But feelings aren't data."

> "I measured. I compared. I learned."

> "Thank you. Any questions?"

**Speaker note:** End with confidence. Pause. Make eye contact. Wait for questions.

---

# Rubric Checklist

| Category | Marks | How This Presentation Hits It |
|---|---|---|
| **Knowledge** | /15 | Explains sensor tech, I2C, variables, evaporation, heat transfer |
| **Thinking** | /25 | Hypothesis with reasoning, fair test design, controlled variables, 3-location comparison, 30 data points each |
| **Communication** | /10 | Clean slides, clear structure, confident delivery, visual aids |
| **Application** | /5 | Real-world relevance (server cooling, ventilation, agriculture) |
| **Total** | /55 | |

# Tips for Delivery
- **Don't read the slides** — they're visual anchors, not a teleprompter
- **Pause after big statements** — let them land (Jobs trademark)
- **Make eye contact** — scan the room, don't stare at the screen
- **Speak slightly slower than feels natural** — it makes you sound confident
- **If you don't know an answer**, say "That's a great question — I'd need to look into that" — honesty > bluffing
