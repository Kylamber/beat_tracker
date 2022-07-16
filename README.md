# Beat tracker
Track the times when beat happens in a music.

## Usage
You can import the IPYNB file to your Jupyter, Google Colab, or else. Change the file name to the specified music file
```python
raw = wave.open("music_name.wav")
```

After that you can change the desired beat frequency range in this line of code
```python
magnitudes_rolling = moving_average(midrange_mag, 30)
```
change `midrange_mag` with either `bass_mag`, `midrange_mag`, `high_mag`, `magnitudes`, or `custom_mag`. 
- `bass_mag` is in the range of 20 Hz to 250 Hz, good for bass/drum beats.
- `midrange_mag` is in the range of 250 Hz to 4000 Hz, good for vocal/note beats.
- `high_mag` is in the range of 4000 Hz and above, good for high-hats beats.
- `magnitudes` is in the range of all of the frequencies, I don't know what this is good for.
- `custom_mag` is in the range of your choices, good for playing around.

At last, run all the code blocks and you'll get the time list.

## Explanation
Using the result from Matplotlib's `specgram` function, we can get the magnitudes of each frequencies. Summing the magnitudes for each frequencies in a time using `np.sum(spectrum, axis=0)`, smoothing it using moving average, and finding the peaks, we get the times where the beat is. It's not the best, but it kinda works.

## Requirements
- Matplotlib
- Scipy
- Numpy
- Wave
