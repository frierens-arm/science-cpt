# Science CPT Speaker Script — Microclimate Monitoring

> **Style**: Confident, conversational, like you are telling a friend about something cool you built.
> **Tip**: Don't read the slides. The slides are visuals. YOU tell the story.
> **Total time**: ~10-12 minutes

---

## Slide 1 — Title
*"Microclimate Monitoring"*

**Script:**
> "What if I told you that the air five steps to your left might have completely different temperature and humidity than where you are standing right now?"

**Say your name + course code.**

**Pause. Let them look at the slide. Move on.**

---

## Slide 2 — The Question

**Script:**
> "I walk past a pond every morning and it always feels damp. My homelab feels like a furnace. But I started thinking — am I just imagining it? Like, are my senses right?"

> "So I put a DHT11 sensor at three spots — at a pond, in my homelab, and in a hallway. Five minutes each. Temperature and humidity. Real numbers, not just feelings."

---

## Slide 3 — Hypothesis
*"If a DHT11 sensor is placed in three different microenvironments..."*

**Script:**
> "Before I collected any data, I made a prediction."

> "I predicted that places near water would show higher humidity, and places near electronics would show higher temperature — compared to a neutral indoor spot."

> "This makes sense because evaporation releases water vapor into the air around a pond, raising humidity. And electronics convert electrical energy into heat. Both things we know — but I wanted to measure how much of a difference they actually make."

---

## Slide 4 — Research Question
*"How do temperature and humidity readings vary across three different microenvironments?"*

**Script:**
> "Here is my research question. It is specific and testable:"

> "How do temperature and humidity vary across three locations — outdoor near water, indoor near electronics, and a neutral indoor spot — all sampled for five minutes each?"

> "Three locations. Five minutes each. Temperature and humidity. Keeping everything else the same so the only variable is where the sensor is."

---

## Slide 5 — Variables

**Script:**
> "In any experiment, you need to be clear about your variables — what changes, what you measure, and what stays the same."

> "My independent variable — the thing I changed — was the location. Pond edge, homelab, and hallway as a control."

> "My dependent variables — what I measured — were temperature in Celsius and relative humidity in percent."

> "The controlled variables — kept the same — were the sensor, the Pi, the five-minute duration, ten-second sampling, and time of day."

---

## Slide 6 — Equipment

**Script:**
> "Here is what I used."

> "A Raspberry Pi 5 — a small computer. A DHT11 digital temperature and humidity sensor connected to a GPIO pin. And a Unicorn HAT Mini — that is a small LED matrix display on top of the Pi. I programmed it to show weather, time, temperature, and humidity."

> "Breadboard, jumper wires, a power bank to take it outside, and a laptop to SSH in and start the script remotely."

> "The whole thing cost under $50 in parts."

---

## Slide 7 — The Three Locations

**Script:**
> "Three spots."

> "First: at the edge of a pond. Outdoor, shaded, near standing water. I expected higher humidity here because of evaporation."

> "Second: my homelab. Servers and networking gear, all running, generating heat. I expected the highest temperature here."

> "Third: a hallway indoors. No strong heat sources, no moisture. This is my control — the baseline to compare the other two against."

---

## Slide 8 — Method

**Script:**
> "The procedure is simple and repeatable."

> "Wire the sensor to the Pi. Write the Python script. Then visit each location, place the sensor down, start the script, wait five minutes, and move to the next one."

> "The script logs a reading every ten seconds. That is 30 readings per location. Same Pi, same sensor, same script — only the location changes."

> "That is what makes this a fair test."

---

## Slide 9 — The Code
*"~20 lines. Simple. Clean. Does one thing well."*

**Script:**
> "Here is the code. And honestly, it is beautiful in its simplicity — about 20 lines."

> "It imports the DHT11 library, sets up the sensor on GPIO pin D4, and then runs a loop: read the sensor, write to a CSV file, wait 10 seconds, repeat. After 5 minutes, it saves the file and stops."

> "One thing to point out — the LOCATION variable is just a string. I change it before each run, and it names the output CSV file. That way I know exactly which data belongs to which location."

---

## Slide 10 — Results

**Script:**
> "So here is what I actually found. These are real numbers from 30 readings at each location."

> "The pond edge came in at 17.8 degrees with 82% humidity. That is cool and damp — exactly what you would expect near standing water."

> "The homelab was the hottest at 27.4 degrees, with humidity dropping to 34%. The servers push out heat, and warm air holds moisture differently, so the relative humidity reads lower."

> "And the hallway — the control — sat at 22.2 degrees and 47% humidity. Normal indoor conditions."

---

## Slide 11 — Data Visualization

**Script:**
> "Let me show you what the data looks like visually."

> "On the left, this bar chart compares temperature and humidity across all three locations. You can clearly see the pond has the highest humidity bar — 82% — while the homelab has the highest temperature bar at 27.4. The hallway sits right in the middle for both."

> "On the right, this is a time series — temperature over the full 5 minutes at each location. The pond temperature is almost flat, which makes sense because water holds temperature steady. The homelab fluctuates a little — probably server fans kicking on and off. And the hallway is the most stable of all."

> "Each dot is one reading every 10 seconds. 30 readings per location."

---

## Slide 12 — Data Analysis

**Script:**
> "Now let me dig into the numbers a bit more. I calculated the mean, median, mode, and range for both temperature and humidity at each location."

> "The mean is the average. The median is the middle value. The mode is the most frequent reading. And the range is max minus min."

> "For the pond, the temperature range is only 1.0 degree — very stable. Water holds temperature steady. But you can also see the pond only has 3 distinct temperature values. That is because the DHT11 has 0.5 degree resolution. So the sensor can only report in half-degree steps. That is a sensor limitation, not a sign nothing changed."

> "The homelab had the biggest temperature range at 2.2 degrees. The hallway humidity mode is 47, same as the mean and median — rock solid."

---

## Slide 13 — Key Findings

**Script:**
> "Here is the bottom line."

> "The homelab was about 9.6 degrees warmer than the pond edge. That is a huge difference — almost 10 degrees — between two spots in the same building complex."

> "And the humidity gap was even more dramatic. The pond was 82% humidity versus 34% in the homelab. That is a 48 percentage point difference."

> "My hypothesis was supported. Water raises humidity. Electronics raise temperature. But now I have the actual numbers to back it up — not just a guess."

---

## Slide 14 — Limitations & Sources of Error

**Script:**
> "No experiment is perfect. Being honest about limitations is part of science."

> "The DHT11 sensor has a margin of error of plus or minus 2 degrees and plus or minus 5% humidity. That means the real pond temperature could be as low as 15.8 or as high as 19.8. That is a big range when you are trying to compare locations."

> "We only sampled 5 minutes per location. If a cloud passed over or a server fan kicked in during those 5 minutes, the data would look different. A longer window would smooth that out."

> "And we tested all three spots in one 20-minute window on one day. Time of day, sunlight, weather — all of these change microclimates. One snapshot does not show the full picture."

> "If I were to redo this, I would sample for 30 minutes or more, across multiple days, with a backup sensor to cross-check."

---

## Slide 15 — When Things Go Wrong

**Script:**
> "One more thing — and this is actually kind of funny. The DHT11 sensor module broke before the demo."

> "I tried to solder the sensor to a header so it could plug into the Pi properly. But after that, it just stopped working. Would not give any readings at all."

> "So for the live display on the Unicorn HAT Mini, I swapped in the OpenWeatherMap API for temperature. It pulls the current outdoor temperature from a weather service instead. It is not the same as a live sensor, but it still shows the Pi can display real weather data."

> "The display still works. It still shows weather, time, and humidity. Just not from a live sensor anymore."

> "I learned that soldering matters. A bad connection can kill a whole component. Next time I would use a breadboard first to test before making anything permanent."

---

## Slide 16 — Why It Matters
*"Microclimates affect comfort, energy use, and even hardware lifespan."*

**Script:**
> "So why does any of this matter?"

> "Server rooms that overheat cost companies millions in cooling. We found a 9.5 degree difference between two rooms in the same building — that is the kind of gap that kills hardware."

> "Greenhouses need 60 to 80 percent humidity for most crops. Our pond edge hit 82 percent. Homes need 30 to 50 percent for comfort — our hallway sat right at 47 percent."

> "Understanding microclimates with real data helps us make better decisions — about where to put computers, how to ventilate a building, or where to plant a garden."

> "Data over assumptions."

---

## Slide 17 — Works Cited

**Script:**
> "Here are my sources, in MLA format."

---

## Slide 18 — Closing
*"Data Over Assumptions"*

**Script:**
> "That is really what this project is about. We make assumptions about our environment every day — 'it feels warmer in here' or 'it is more humid outside.' But feelings are not data."

> "We measured. We compared. We learned."

> "Thank you. Any questions?"

**Speaker note**: End with confidence. Pause. Make eye contact. Wait for questions.

---

# Tips for Delivery
- **Don't read the slides** — they are visual anchors, not a teleprompter
- **Pause after big statements** — let them land
- **Make eye contact** — scan the room, do not stare at the screen
- **Speak slightly slower than feels natural** — it makes you sound confident
- **If you do not know an answer**, say "That is a great question — I would need to look into that" — honesty over bluffing
