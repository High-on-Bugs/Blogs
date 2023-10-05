---
title: "Striking the Right Chord: Gaming and Beyond with Python-Powered Audio Magic"
datePublished: Thu Oct 05 2023 18:05:40 GMT+0000 (Coordinated Universal Time)
cuid: clndhnaiu000709l7dc3z6cny
slug: sows
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1696528699376/123ad5c6-b8db-4a2a-9552-2ffb39ac9c54.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1696529125056/168f8a06-e71d-4c54-b25e-c38726cca573.jpeg
tags: python, audio, guitar

---

Okay! I agree the title sounds too overly technical. Long story short, I made a program to play Counter-Strike using my guitar. Why write a blog about a program that lets you play Counter-Strike with a guitar? Well, truth be told, it doesn't have much practical use. So why bother? The reason is to spotlight the valuable building blocks within the project that could benefit you.

If you want to check the software out for yourself, visit the [SOWS Website](https://sows.sbk2k1.tech/).

Here is an early usage video of the software.

%[https://www.youtube.com/watch?v=NNfp-58yXsA] 

So let us get into answering the questions of how and why.

## Introduction

### Capabilities

1. **Driver-Swapping Wizardry**: This thing can seamlessly switch between different audio drivers. Whether you're rocking out with your trusty headphones or getting all fancy with an audio interface, it's got your back.
    
2. **Audio Detective Mode**: You can stop actions and see the notes you are producing. So in theory you can replace your guitar tuner. (Not Recommended)
    
3. **Musical Notes Meet Gaming Actions**: Here's the kicker – it takes those signals, turns them into musical notes, and then maps those notes to in-game actions. Picture strumming a power chord to toss a grenade or hitting a sweet riff to reload your weapon. It's not that crazy. (Yet?)
    

### **Motivation Behind the Madness:**

Now, you're probably wondering why in the world someone would come up with this concoction. Well, I wanted to merge two things I absolutely adore: jamming on the guitar and going all out in Counter-Strike. The wild and wacky creations of developers like [Michael Reeves](https://www.youtube.com/@MichaelReeves) were a catalyst. He showed me that the craziest ideas can lead to the most fun and innovative projects.

# I. The Foundations

### Section 1.1: **Python Object-Oriented Programming (OOP)**

**Importance of OOP in Software Development:** Object-oriented programming (OOP) is the backbone of many modern software projects, and it plays a crucial role in making code more organized, modular, and maintainable. It's like building with Lego bricks; you create reusable components (objects) with their own data and behavior, making it easier to manage complexity as your project grows.

**Project Structure Using Python Classes and Objects:** In my project, we've leveraged OOP to structure the code effectively. Let's take a quick peek at how it's done:

```python
class Ui_MainWindow:
    # This class handles the user interface of my application.
    # It's structured using Qt Designer and PyQt5.

class CustomEventFilter:
    # CustomEventFilter is a class designed to filter and process user input events.
    # It prevents keyboard mappings from interacting with the program itself

class ActionHandler:
    # ActionHandler is responsible for mapping audio signals to specific in-game actions.
    # It encapsulates the logic for translating guitar sounds into game commands.

class AudioProcessingThread:
    # AudioProcessingThread is a separate thread that handles audio detection and processing.
    # This ensures that audio-related tasks don't block the main application thread.
```

**Code Examples Illustrating Key OOP Concepts:** Let's delve into some code snippets to see OOP concepts in action within my software:

```python
# Example of Encapsulation
class ActionHandler:
    def __init__(self):
        self.actions = {}  # This dictionary encapsulates our actions and their corresponding mappings.

# Example of Inheritance
class CustomEventFilter(QEventFilter):
    def __init__(self):
        super().__init__()  # We inherit the behavior of QEventFilter to customize event handling.

# Example of Polymorphism
class AudioProcessingThread(QThread):
    def run(self):
        # Here, we override the 'run' method to provide our behavior while utilizing QThread's functionality.
```

### **Section 1.2: Desktop Application with PyQt5 and PySide**

**Choice of PyQt5 and PySide:** I opted for PyQt5 and PySide to create the desktop application because of my past (yet limited) experience working with it for [Mnemosyne](https://mnemosyne.sbk2k1.tech/).

**Creating a Desktop App in Python:** Building a desktop app in Python using PyQt5 and PySide involves several steps:

1. **Designing the UI**: We've used Qt Designer to design the user interface. It allows for a visual drag-and-drop interface design, which simplifies the process.
    
2. **Creating the Main Window**: We've created a `Ui_MainWindow` class to set up the main window of the application. This class is generated based on previously created UI design.
    
3. **Event Handling**: The `CustomEventFilter` class handles user input events, ensuring that the app is not affected by actions triggered by the audio.
    
4. **Threading**: To keep the app responsive, we use the `AudioProcessingThread` class to handle audio detection in a separate thread, preventing the main thread from being blocked.
    

**Showcasing the User Interface:** My user interface, designed with PyQt5 and PySide, provides an intuitive way to interact with the application. Users can select audio drivers, visualize audio input, start a test mode to check out the note detected, and review the controls.

That's the foundation of the project structure and how I harnessed OOP principles to keep things organized and manageable while creating a desktop application using PyQt5 and PySide. These elements work in harmony to bring the magic of playing Counter-Strike with a guitar to life!

## II. Audio Processing

### Section 2.1: **Audio Driver Integration**

***Interacting with Audio Drivers****:* In the heart of the software, there's a crucial component that enables the magic to happen - the interaction with audio drivers. This interaction allows us to tap into the audio data from your audio driver and make sense of it. Here's a glimpse of how it works:

Our software utilizes the [PyAudio](https://pypi.org/project/PyAudio/) library to manage audio input. With PyAudio, we can establish connections with audio drivers, be it your headphone drivers or any audio interface you prefer. This gives us access to the raw audio data that flows through your system.

***Challenges and Considerations****:* Working with audio interfaces presents its fair share of challenges. Ensuring compatibility across a wide range of drivers and hardware configurations can be tricky. We must consider issues like latency, device selection, and data format when dealing with these interfaces.

To tackle these challenges, I configured the software with the following settings:

```python
# Audio settings
self.buffer_size = 1024
self.pyaudio_format = pyaudio.paFloat32
self.n_channels = 1
self.samplerate = 48000
self.lowest_pitch = 5
self.testing = False
```

These settings help us ensure that the audio input is processed efficiently and that the guitar notes are captured accurately.

**Code Snippets:** Here's an example of how we set up the audio stream with PyAudio in the software:

```python
# Initialize PyAudio
audio = pyaudio.PyAudio()

# Configure audio stream
self.buffer_size = 1024
self.pyaudio_format = pyaudio.paFloat32
self.n_channels = 1
self.samplerate = 48000

# Open an audio stream
self.stream = audio.open(format=self.pyaudio_format,
                         channels=self.n_channels,
                         rate=self.samplerate,
                         input=True,
                         frames_per_buffer=self.buffer_size)
```

This code establishes a connection with the audio driver, configures the audio stream, and prepares to receive audio data from your guitar.

### Section **2.2: Fourier Transform for Frequency Analysis**

***Introduction to Fourier Transform****:* Imagine you have a complex sound, like the music from your guitar. This sound is made up of various individual musical notes. It is a mixture of different waveforms with varying frequencies rather than a single waveform with consistent identifiable parameters.

Here's how it works:

1. **Sound Waves as Building Blocks:** Sound is a wave, and complex sounds are made up of simpler waveforms. Each musical note you play on your guitar can be thought of as a unique waveform.
    
2. **Breaking Down the Sound:** The Fourier Transform takes the complex sound and breaks it down into these simple waveforms, sort of like taking a big jigsaw puzzle and separating it into its individual pieces.
    
3. **Frequency Analysis:** Each of these simple waveforms represents a specific musical note, and they have different frequencies.
    
4. **Quantifying the Notes:** The Fourier Transform quantifies how much of each of these simple waveforms is present in the complex sound. It tells us, "Hey, you've got a lot of this note, a little of that note," and so on.
    

So, in a nutshell, the Fourier Transform is like a magical tool that takes a complex sound, dissects it into its individual musical notes, and tells us how much of each note is in there. It's like breaking down a song into its musical ingredients, and it's incredibly useful in understanding and working with sounds in various fields, from music to engineering.

You can check out this amazing video from 3B1B to get it:

%[https://www.youtube.com/watch?v=spUNpyF58BY&t=850s] 

***Role of Fourier Transform****:* The Fourier Transform is a go-to technique for dissecting audio signals. It breaks down complex sound waves into their individual frequency components. For us, this means identifying the notes your guitar is playing by examining the frequency of the sound.

***Fourier Transform Implementation****:* Here's a high-level overview of how we implement the Fourier Transform in the software:

```python
import aubio
# Initialize the Fourier Transform object
pitches = aubio.pitch("yin", self.buffer_size, self.buffer_size, self.samplerate)
# Perform the Fourier Transform on audio data
pitches, conf = pitches(self.audio_data)
# Extract the pitch (frequency) information
pitch_frequency = pitches[0]
```

In this code snippet, we use the Aubio library to create a pitch detection object. We then feed it the audio data, and it returns the pitch or frequency information. This frequency data is what we use to map guitar notes to in-game actions.

So, there you have it! We've unveiled how the software handles audio drivers, grapples with audio interfaces, and employs the Fourier Transform to turn your guitar sounds into a symphony of gaming actions. With these elements in play, you're one step closer to rocking out in Counter-Strike like never before!

## III. **Mapping Audio Frequencies to Actions**

***Mapping Audio Frequencies to Actions****:* Now, let's delve into the exciting part – mapping the frequencies generated by your guitar to specific keyboard and mouse actions within the software. This is where the magic happens! We've got a dictionary of musical notes, and each note corresponds to a unique action, such as moving, shooting, or jumping.

***Examples of Frequency-to-Action Mapping****:* Here's a sneak peek at how some musical notes translate into actions:

* When you play the note "C," it's like moving forward in the game.
    
* If you hit "D," it's equivalent to moving backward.
    
* "G#" on your guitar will make your character jump in the game.
    
* "A#" triggers shooting, while "B" initiates a reload.
    

These mappings allow you to control your game character by playing your guitar. It's like turning your guitar into a gaming controller!

*Toggles and Logic:* But hold on, there's more! The software incorporates toggles and logic to make the gameplay experience smoother. For instance, if you play the "A" note, it toggles crouching on or off. So, the first "A" press crouches, and the next one stands your character back up. This smart logic ensures that you have control over these actions without any fuss. Moreover, we control 2D movement using a List of Movements across X and Y dimensions. Let's break down the logic and usage of lists in these functions:

```python
# function to move forward or stop moving backwards
def moveForward(self):
    if self.navigation_mapping[0] == None:
        self.navigation_mapping[0] = 1
        keyboard.press('w')
    elif self.navigation_mapping[0] == -1:
        self.navigation_mapping[0] = None
        keyboard.release('s')
```

this code, we have a function called `moveForward` that is responsible for moving your character forward in the game. Here's how it works:

1. `self.navigation_mapping` is a list used to keep track of your character's movement in two directions: forward/backward (index 0) and left/right (index 1).
    
2. When you call `moveForward`, the function first checks if `self.navigation_mapping[0]` is `None`. This check ensures that if you're already moving backward (indicated by `-1`), you won't start moving forward again immediately.
    
3. If `self.navigation_mapping[0]` is indeed `None`, it sets it to `1` to indicate that your character is now moving forward. Additionally, it simulates a key press of the 'w' key using [`keyboard.press`](http://keyboard.press)`('w')`.
    
4. However, if `self.navigation_mapping[0]` is `-1`, it means your character is currently moving backward. In this case, the function sets `self.navigation_mapping[0]` back to `None` to stop moving backward and releases the 's' key to stop moving in that direction.
    

This logic ensures that your character can smoothly switch between moving forward and stopping moving backward, allowing for responsive and intuitive control.

Similar logic applies to the `moveBackwards` and `moveLeft` functions, where the list `self.navigation_mapping` is used to keep track of the character's movement in different directions, and key presses and releases are simulated accordingly to provide seamless control over your character's movement.

## IV. Practical Applications

### Section 4.1: Practical Applications

Nothing! Helping you understand the different parts used in making the software and instigating ideas.

### Section 4.2: Creative Possibilities

*Brainstorm Your Own Ideas:* I encourage you to think outside the box. This software is a canvas for your creativity. Pick out individual parts and apply them to your own ideas.

## V. Conclusion and Further Exploration

***Summarizing the Journey****:* In this blog post, we've embarked on a journey into the world of using your guitar as a gaming controller. We've explored the technical aspects, mapped out actions, and even dabbled in the potential beyond just gaming with your guitar.

***Unleash Your Creativity****:* The software is a starting point for your own tech adventures. We invite you to explore each element in more detail. Dive into Python Object-Oriented Programming, discover the wonders of audio processing, and experiment with game development or other fields. Here are some resources to get you started:

* [Link to Python Documentation](https://www.python.org/doc/): Learn more about Python, and the language behind the software.
    
* [Link to PyQt Documentation](https://doc.qt.io/qtforpython-6/): Learn about the framework used to make GUIs
    
* I'm sure you can look around for other stuff yourself. :)
    

## Call to Action

Now, it's your turn! Download the software, give it a whirl, and share your experiences with us. We'd love to hear your feedback and suggestions for improvement. Join us in this journey of creativity and innovation, where music meets technology in exciting ways. Who knows what you'll come up with next?

I can also make it an Open-Source Project. Some features I would love to add.

* Customizable Actions.
    
* A Desktop overlay while playing games that shows active buttons.
    
* Suggest your own.
    

My Socials - [here](https://t.co/OmrSzziq5s)!

---

If you still have any questions/queries you can reach out to me on my [**LinkedIn**](https://www.linkedin.com/in/sbk2k1/) / [**GitHub**](https://github.com/sbk2k1) / [**Twitter**](https://twitter.com/sbk_2k1).

Cheers!