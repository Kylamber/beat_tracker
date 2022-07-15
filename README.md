# beat_tracker
Track the times when the beat happens in a music.

## Usage
You can import the IPYNB file to your Jupyter, Google Colab, or else. Change the file name to the specified music file
```python
raw = wave.open("music_name.wav")
```

Run all the code blocks and you'll get the time list.

## Explanation
Using the result from Matplotlib's `specgram` function, we can get the magnitudes of each frequencies. Summing the magnitudes for each frequencies in a time using `np.sum(spectrum, axis=0)`, smoothing it using moving average, and finding the peaks, we get the times where the beat is. It's not the best, but it kinda works.

## Requirements
- Matplotlib
- Scipy
- Numpy
- Wave
