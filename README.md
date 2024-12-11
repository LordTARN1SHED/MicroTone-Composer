# MicroTone-Composer

## Introduction
This project involves creating a mini piano using a microcontroller. It features an interactive musical instrument with a buzzer for sound output, an LCD for displaying musical scores, and a keypad for user input. The piano supports both real-time playing and playback of preloaded songs, with visual feedback on the LCD.

## Objectives
- Consolidate knowledge of hardware and software concepts learned throughout the semester.
- Explore the capabilities of components like buzzers and LCDs for creating innovative features such as music playback and animated displays.

## Features
1. **Interactive Playing**: Play notes by pressing corresponding keys on the keypad, with the buzzer outputting the respective tones.
2. **Preloaded Music**: Includes pre-recorded songs such as *Canon* and *漠河舞厅 (Mohe Ballroom)*, which can be played at the press of a button.
3. **LCD Display**: Displays musical notes and animated effects in real-time, enhancing the user experience.
4. **Adjustable Octaves**: A toggle switch enables shifting notes across four octaves, allowing for a broader range of musical expression.
5. **Robust Design**: Handles complex operations like simultaneous music playback and LCD updates without performance issues.

## Hardware Used
- **LCD Display**: Displays musical notes and animations.
- **CH451 Keypad**: Handles user input.
- **Buzzer**: Outputs musical tones.
- **Toggle Switch**: Adjusts the octave range.
  
### Hardware Connections
- **LCD**: IO1-IO4 connected to WR, RS, RST, DE.
- **Buzzer**: PWM0 connected to BEEP.
- **Keypad**: CAP0, SDA, SCL connected to LOAD, DIN, SLCK.
- **Other Connections**: DOUT to INT0, CADC0, CDAC0 to k1, k2.

## Challenges and Solutions
1. **Memory Overflow**:
   - Problem: Large data sets for LCD animations and preloaded music exceeded memory limits.
   - Solution: Declared constants with `code` to store them in program memory and adjusted compiler settings for larger program size.

2. **LCD Display Issues**:
   - Problem: Displayed patterns appeared garbled.
   - Solution: Configured correct control words and ensured the LCD was in graphical display mode.

3. **Alignment Problems**:
   - Problem: Display elements were misaligned.
   - Solution: Divided the screen into defined regions and implemented precise positioning logic.

4. **Buzzer Interruptions**:
   - Problem: Timer conflicts caused interruptions during sound playback.
   - Solution: Set timer priorities to ensure uninterrupted buzzer operation.

5. **Display Performance**:
   - Problem: Frequent LCD updates caused delays in music playback.
   - Solution: Optimized LCD updates to occur during timer interrupts and adjusted playback logic accordingly.

## Key Functions
- **Sound Frequency Calculation**: 
  - Formula: `65536 - (1/2f)/(11/11.0592MHz)`
- **Sing Function**: A helper function to simplify song implementation by specifying note pitch and duration.
- **Animation Logic**: Handled dynamic updates for LCD animations synchronized with user interactions and music playback.

## Lessons Learned
This project deepened our understanding of microcontroller programming, hardware interfacing, and system optimization. Overcoming challenges like memory constraints and real-time performance issues provided valuable experience in embedded systems design.

## Future Work
- Expand the library of preloaded songs.
- Enhance LCD animations for more immersive visual effects.
- Explore additional sensors for expanded interaction capabilities.
