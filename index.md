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

## 2. "Fugue in Bb Minor" (original composition)
* [Link to repo](https://github.com/allolib-s23/demo1-gracefeng05/blob/main/tutorials/synthesis/harpsichord.cpp)
* Instructions to play: run ```./run.sh tutorials/synthesis/interstellar.cpp``` and press 'f'
* Using Christine Tu's MIDI to json conversion, I composed a short fugue in MuseScore to be played in AlloLib by the plucked string preset. This project was my first attempt at changing the sound to emulate an instrument (harpsichord). I did so by changing the ADSR to have a stronger attack and less decay. I also made the sound slightly "warmer" by following Adam Schmieder's notes on synthesis.

## 3. "Organon" (original composition)
* [Link to repo](https://github.com/allolib-s23/demo1-gracefeng05/blob/main/tutorials/synthesis/organon.cpp)
* Instructions to play: run ```./run.sh tutorials/synthesis/organon.cpp``` and press 'o'
* Again using Christine Tu's MIDI to json conversion, I experimented with graphics that matched their respective sounds. By applying a randomized rotation to the cube mesh, I created an illusion of vibration that intensified as the note sustained.

## 4. 
