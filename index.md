# Notes from Grace Feng

# Final Summary

## 1. "Cornfield Chase" from *Interstellar*, Hans Zimmer
* [Link to repo](https://github.com/allolib-s23/demo1-gracefeng05/blob/main/tutorials/synthesis/interstellar.cpp)
* Instructions to play: run ```./run.sh tutorials/synthesis/interstellar.cpp``` and press 'i'
* I chose this piece because it's largely composed of repeated patterns and phrases. Using my arpeggiator function, I was able to arrange the piece without much hardcode -- I simply passed the chords as vectors into my function and specified how long each arpeggio would span. Doing so taught me how complex melodies can often be abstracted. I also played with the graphics by adding multiple meshes to one instrument, creating sparkly visuals.

### Arpeggiator Function(s):
* upDownArp(int bpm, float startTime, int measures, const std::vector<float>& frequencies, int octaves)
  - Arpeggiates up and down the vector for the specified number of octaves
  - Completes 1 period (up and down) per measure -- this determines each note's duration along with bpm input
 * bpmPhaseShift(int bpm, float startTime, int measures, vector<float>& frequencies, int octaves)
  - Plays each note in a chord at a different bpm starting with 1st note at input bpm, 2nd at input bpm - 2, 3rd at input bpm - 4, etc.
  - Just a cool demonstration of how notes syncopate at different tempos + cool visuals.
  - [Link to recording](https://drive.google.com/file/d/15U_BEBhX7YK3KufUB6bmi0IaGfkXCCv7/view?usp=sharing)

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
* This time, I converted my piece from Logic Pro. Unlike my previous pieces, it was originally written for synth sounds (which I found in Logic Pro). I attempted to recreate these Logic Pro sounds by tweaking Adam Schmieder's SubSyn presets. This project was challenging because I started with an expectation of what the instruments should sound like based on my Logic Pro project. As a result, I was unsatisfied with most of my AlloLib imitations. For example, I couldn't get my synth bass to sound as rich and sawy as the one in LogicPro, and my electric bass mock-up lacked the attack and dimension of a real electric bass no matter how much I fiddled with the attack, curve, and envelope. Also, I found that low frequencies in AlloLib lack brightness, so I had to tranpose most of my bass lines uptwo octaves to prevent the piece from getting muddy.

A big takeaway from this project was to compose *for* the instruments. If I'd known the limitations in advance (low frequencies, lag from heavy instrumentation, non-organic "digital" sounds), I'd have optimized my piece.
