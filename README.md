# Notes from Grace Feng

# Final Summary

## 1. "Cornfield Chase" from *Interstellar*, Hans Zimmer
* [Link to repo](https://github.com/allolib-s23/demo1-gracefeng05/blob/main/tutorials/synthesis/interstellar.cpp)
* Instructions to play: run ```./run.sh tutorials/synthesis/interstellar.cpp``` and press 'i'
* I chose this piece because it's largely composed of repeated patterns and phrases. Using my arpeggiator function, I was able to arrange the piece without much hardcode -- I simply passed the chords as vectors into my function and specified how long each arpeggio would span. Doing so taught me how complex melodies can often be abstracted. I also played with the graphics by adding multiple meshes to one instrument, creating sparkly visuals.

## Arpeggiator Function(s)

Each arpeggiator includes built-in dynamics, allowing notes to vary in amplitude or velocity based on position, direction, or time. This adds musical expressiveness and avoids the robotic feel of uniform note playback.

#### `upDownArp(int bpm, float startTime, int measures, const std::vector<float>& frequencies, int octaves)`

* Arpeggiates up and down through the frequency vector for the specified number of octaves.
* Completes one full cycle (ascending + descending) per measure — note duration is determined by both BPM and measure count.
* Built-in dynamics gradually increase during ascent and fade during descent, emulating a natural phrasing curve.
* Useful for creating continuous, wave-like melodic motion reminiscent of classic synth arpeggiators.

#### `bpmPhaseShift(int bpm, float startTime, int measures, std::vector<float>& frequencies, int octaves)`

* Assigns a unique BPM to each note in a chord:

  * 1st note plays at the input BPM,
  * 2nd note at *BPM − 2*,
  * 3rd at *BPM − 4*, and so on.
* Produces phase-shifted rhythmic motion, resulting in syncopated, drifting polyrhythms.
* Built-in dynamics apply a subtle amplitude modulation per note to emphasize shifting accents as phases drift apart.
* Great for visualizing rhythmic interference patterns — each note’s tempo can also drive its own visual oscillator.
* [Link to recording](https://drive.google.com/file/d/15U_BEBhX7YK3KufUB6bmi0IaGfkXCCv7/view?usp=sharing)

#### `randomWalkArp(int bpm, float startTime, int measures, const std::vector<float>& frequencies, float wanderChance)`

* Introduces stochastic movement by randomly stepping up or down the vector with a given probability (`wanderChance`).
* Inspired by Logic Pro’s *Random Order* arpeggiator mode — generates endlessly evolving melodic textures.
* Built-in dynamics assign random velocity variations per step to mimic humanized playing.

#### `gateSwingArp(int bpm, float startTime, int measures, std::vector<float>& frequencies, float swing, float gateLength)`

* Adds groove by delaying every other step by a fraction of a beat (`swing`).
* Controls each note’s articulation via `gateLength`, adjusting how long a note sustains relative to its duration.
* Built-in dynamics emphasize downbeats and slightly soften offbeats to reinforce rhythmic swing.
* Simulates the rhythmic feel of analog hardware sequencers.

#### `chordLatchArp(int bpm, float startTime, int measures, std::vector<float>& chordProgression, bool retrig)`

* Holds (or *latches*) a chord until a new trigger event occurs.
* If `retrig = true`, the pattern restarts with each new chord; otherwise, chords blend seamlessly into one another.
* Built-in dynamics fade in with each new chord and fade out before the transition, creating smooth harmonic flow.
* Ideal for creating sustained rhythmic beds or evolving harmonic progressions.

#### `patternMorphArp(int bpm, float startTime, int measures, std::vector<float>& frequencies, std::vector<int> patternA, std::vector<int> patternB, float morphSpeed)`

* Interpolates between two rhythmic patterns (`patternA` → `patternB`) over time.
* Enables smooth morphing between motifs, emulating advanced step-sequencer behavior.
* Built-in dynamics interpolate between velocity curves of `patternA` and `patternB`, reinforcing the sense of motion.
* Useful for designing dynamic, evolving arpeggios that gradually shift groove or emphasis.

These custom arpeggiators were inspired by the design of real synth instruments in Logic Pro.

## 2. "Organon" (original composition)
* [Link to repo](https://github.com/allolib-s23/demo1-gracefeng05/blob/main/tutorials/synthesis/organon.cpp)
* Instructions to play: run ```./run.sh tutorials/synthesis/organon.cpp``` and press 'o'
* Using Christine Tu's MIDI to json converter, I experimented with graphics that matched their respective sounds. By applying a randomized rotation to the cube mesh, I created an illusion of vibration that intensified as the note sustained. For the background, I attempted to emulate the sound of a pedaled marimba using a sine wave.

## 3. "String Quintet" (original composition)
* [Link to repo](https://github.com/allolib-s23/demo1-gracefeng05/blob/main/tutorials/synthesis/stringQuintet.cpp)
* Instructions to play: run ```./run.sh tutorials/synthesis/organon.cpp``` and press 'q'
* Using the instrument I created for *Organon*, I composed a "string" quintet. Again, thanks to Christine's MIDI to json converter, I was able to incorporate changes of time signature. This string quintet begins in 5/8 and switches between 5/8 and 6/8 throughout the piece. My main goal with this quintet was to balance voices. I wanted it to be apparent that there were 5 separate voices given that they all shared a digital instrument, making them indistinguishable by the graphics.

## 4. "Miniboss" (original composition)
* [Link to repo](https://github.com/allolib-s23/demo1-gracefeng05/blob/main/tutorials/synthesis/miniboss.cpp)
* Instructions to play: run ```./run.sh tutorials/synthesis/miniboss.cpp``` and press 'm'
* This time, I converted my piece from Logic Pro. Unlike my previous pieces, it was originally written for synth sounds (which I found in Logic Pro). I attempted to recreate these Logic Pro sounds by tweaking Adam Schmieder's SubSyn presets. This project was challenging because I started with an expectation of what the instruments should sound like based on my Logic Pro project. As a result, I was unsatisfied with most of my AlloLib imitations. For example, I couldn't get my synth bass to sound as rich and sawy as the one in LogicPro, and my electric bass mock-up lacked the attack and dimension of a real electric bass no matter how much I fiddled with the attack, curve, and envelope. Also, I found that low frequencies in AlloLib lack brightness, so I had to tranpose most of my bass lines up 2 octaves to prevent the piece from getting muddy.

A big takeaway from this project was to compose *for* the instruments. If I'd known the limitations in advance (low frequencies, lag from heavy instrumentation, non-organic "digital" sounds), I'd have optimized my piece in Logic Pro before converting it to AlloLib.
