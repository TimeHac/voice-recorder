# voice_recorder.py
import sounddevice as sd
from scipy.io.wavfile import write

# Sample rate
fs = 44100

seconds = int(input("Enter the recording time in seconds: "))

print("Recording...\n")

record_voice = sd.rec(int(seconds * fs), samplerate=fs, channels=2, dtype='int16')

sd.wait()

write("MyRecording.wav", fs, record_voice)

print("Recording is done. Please check your folder to listen to the recording.")
