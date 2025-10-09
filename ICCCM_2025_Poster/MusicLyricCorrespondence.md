Music and Lyric Correspondence
================
Nat Condit-Schultz
2025-10-09

In the following analyses, I consider the shared information between
“musical” and “lyrical” features in three datasets of sung music. This
illustrates the degree to which lyric data can shed light on other
aspects of the music.

## Features

- *Musical features*
  - Contour (`up`, `down`, `same`)
  - Melodic interval (e.g., `±M2`)
  - Scale degree (e.g., `#4`)
  - Duration (rounded to powers of 2; e.g., `16`, `8`, `4`, `2`).
  - Procedes rest (`true` or `false`)
- *Lyrical features*
  - Position in word (`single syllable`, `first syllable`,
    `last syllable`, `middle syllable`)
  - Melismatic (`new syllable`, `melisma`)
  - Capitalized word
  - Punctuation (`none`, `,`, `.`)
  - Vowel (vowel characters in each syllable)

I compute “3-grams” of all features.

## Datasets

- 214 songs from the *Coordinated Corpus of Popular Music* (Billboard)
  \[@arthur2023\]
  - Transcribed English lyrics (circa 1955–1991)
- Seven *Oratorios* by G.F. Handel, from MuseData
  \[@selfridge-field2001\]
  - Authorial English lyrics (circa 1708–1752)
- Ninety-one *Cantatas* by J.S. Bach, from MuseData
  (<span class="citation">ibid.</span>)
  - Authorial German lyrics (circa 1707–1750)

## Mutual Information

### Local, normalized (same as poster)

Here, I show the mutual information (shared entropy) of each pair of
features as a proportion of the joint entropy (rounded to two decimal
places). This is calculated independently within each piece/movement,
and the `minimum`–`mean`–`maximum` is shown.

#### Cocopops

<table class="table" style="color: black; margin-left: auto; margin-right: auto;">

<thead>

<tr>

<th style="text-align:left;">

</th>

<th style="text-align:left;">

Contour
</th>

<th style="text-align:left;">

Melodic interval
</th>

<th style="text-align:left;">

Scale degree
</th>

<th style="text-align:left;">

Duration
</th>

<th style="text-align:left;">

Procedes rest
</th>

<th style="text-align:left;">

Position in word
</th>

<th style="text-align:left;">

Melisma
</th>

<th style="text-align:left;">

Capitalized
</th>

<th style="text-align:left;">

Punctuation
</th>

</tr>

</thead>

<tbody>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Melodic interval
</td>

<td style="text-align:left;">

.64–.8–.93
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Scale degree
</td>

<td style="text-align:left;">

.47–.7–.82
</td>

<td style="text-align:left;">

.75–.9–.97
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Duration
</td>

<td style="text-align:left;">

.18–.4–.96
</td>

<td style="text-align:left;">

.25–.5–.82
</td>

<td style="text-align:left;">

.23–.5–.84
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Procedes rest
</td>

<td style="text-align:left;">

.02–.3–.72
</td>

<td style="text-align:left;">

.01–.2–.62
</td>

<td style="text-align:left;">

.02–.2–.64
</td>

<td style="text-align:left;">

.03–.3–.76
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Position in word
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.15–.4–.74</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.17–.4–.72</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.17–.4–.7</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.07–.4–.74</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.04–.3–.98</span>
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Melisma
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.01–0–.05</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–0–.04</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–0–.03</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–0–.07</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.01–.1–1</span>
</td>

<td style="text-align:left;">

.01–0–.07
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Capitalized
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.04–.1–.63</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.04–.2–.55</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.04–.2–.54</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.04–.1–.63</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.03–.1–.48</span>
</td>

<td style="text-align:left;">

.03–.1–.5
</td>

<td style="text-align:left;">

.01–.1–.35
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Punctuation
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.01–.1–.32</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.01–.1–.34</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.01–.1–.34</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.01–.1–.55</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.01–.1–1</span>
</td>

<td style="text-align:left;">

.01–.1–.25
</td>

<td style="text-align:left;">

.02–.5–1
</td>

<td style="text-align:left;">

.01–.1–.35
</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Vowel
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.31–.5–.72</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.34–.7–.86</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.34–.6–.82</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.21–.5–.69</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.01–.2–.39</span>
</td>

<td style="text-align:left;">

.22–.5–.78
</td>

<td style="text-align:left;">

0–0–.1
</td>

<td style="text-align:left;">

.03–.2–.81
</td>

<td style="text-align:left;">

.01–.1–.31
</td>

</tr>

</tbody>

</table>

#### Handel

<table class="table" style="color: black; margin-left: auto; margin-right: auto;">

<thead>

<tr>

<th style="text-align:left;">

</th>

<th style="text-align:left;">

Contour
</th>

<th style="text-align:left;">

Melodic interval
</th>

<th style="text-align:left;">

Scale degree
</th>

<th style="text-align:left;">

Duration
</th>

<th style="text-align:left;">

Procedes rest
</th>

<th style="text-align:left;">

Position in word
</th>

<th style="text-align:left;">

Melisma
</th>

<th style="text-align:left;">

Capitalized
</th>

<th style="text-align:left;">

Punctuation
</th>

</tr>

</thead>

<tbody>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Melodic interval
</td>

<td style="text-align:left;">

.61–.8–1
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Scale degree
</td>

<td style="text-align:left;">

.43–.7–.93
</td>

<td style="text-align:left;">

.65–.9–1
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Duration
</td>

<td style="text-align:left;">

.16–.4–1
</td>

<td style="text-align:left;">

.19–.5–.91
</td>

<td style="text-align:left;">

.21–.5–.88
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Procedes rest
</td>

<td style="text-align:left;">

.07–.3–.73
</td>

<td style="text-align:left;">

.06–.3–.62
</td>

<td style="text-align:left;">

.04–.2–.59
</td>

<td style="text-align:left;">

.09–.3–1
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Position in word
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.11–.3–1</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.17–.4–.85</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.17–.4–.81</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.11–.3–1</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.07–.2–.73</span>
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Melisma
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.01–0–.28</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.01–0–.24</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.01–0–.23</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.02–.1–.29</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.02–.1–.4</span>
</td>

<td style="text-align:left;">

.01–.1–.51
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Capitalized
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.02–.1–.53</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.01–.1–.54</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.01–.1–.51</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.02–.1–.48</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.04–.2–.44</span>
</td>

<td style="text-align:left;">

.03–.1–.42
</td>

<td style="text-align:left;">

.03–.2–1
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Punctuation
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.08–.2–.7</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.13–.3–.69</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.11–.3–.66</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.08–.3–.83</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.09–.3–.83</span>
</td>

<td style="text-align:left;">

.09–.2–.58
</td>

<td style="text-align:left;">

.02–.1–.67
</td>

<td style="text-align:left;">

.03–.2–.75
</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Vowel
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.19–.6–1</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.22–.7–1</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.24–.7–.99</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.2–.4–1</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.07–.3–.73</span>
</td>

<td style="text-align:left;">

.26–.5–1
</td>

<td style="text-align:left;">

.01–0–.28
</td>

<td style="text-align:left;">

.02–.2–.55
</td>

<td style="text-align:left;">

.12–.3–.69
</td>

</tr>

</tbody>

</table>

#### Bach

<table class="table" style="color: black; margin-left: auto; margin-right: auto;">

<thead>

<tr>

<th style="text-align:left;">

</th>

<th style="text-align:left;">

Contour
</th>

<th style="text-align:left;">

Melodic interval
</th>

<th style="text-align:left;">

Scale degree
</th>

<th style="text-align:left;">

Duration
</th>

<th style="text-align:left;">

Procedes rest
</th>

<th style="text-align:left;">

Position in word
</th>

<th style="text-align:left;">

Melisma
</th>

<th style="text-align:left;">

Capitalized
</th>

<th style="text-align:left;">

Punctuation
</th>

</tr>

</thead>

<tbody>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Melodic interval
</td>

<td style="text-align:left;">

.53–.7–.96
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Scale degree
</td>

<td style="text-align:left;">

.28–.6–.95
</td>

<td style="text-align:left;">

.36–.9–1
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Duration
</td>

<td style="text-align:left;">

.11–.3–.73
</td>

<td style="text-align:left;">

.19–.5–.74
</td>

<td style="text-align:left;">

.17–.4–.72
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Procedes rest
</td>

<td style="text-align:left;">

.05–.2–.51
</td>

<td style="text-align:left;">

.03–.2–.47
</td>

<td style="text-align:left;">

.03–.2–.46
</td>

<td style="text-align:left;">

.06–.2–.66
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Position in word
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1–.3–.68</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.21–.5–.73</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.17–.4–.73</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1–.2–.51</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.06–.2–.33</span>
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Melisma
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.01–0–.1</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.01–0–.08</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.01–0–.09</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.01–.1–.19</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.01–.1–1</span>
</td>

<td style="text-align:left;">

.02–0–.15
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Capitalized
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.03–.2–.52</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.02–.3–.54</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.02–.2–.51</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.04–.1–.39</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.04–.1–.37</span>
</td>

<td style="text-align:left;">

.05–.2–.54
</td>

<td style="text-align:left;">

.03–.1–.67
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Punctuation
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.08–.2–.44</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1–.3–.47</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.09–.2–.5</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.07–.2–.46</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.08–.3–.95</span>
</td>

<td style="text-align:left;">

.1–.2–.58
</td>

<td style="text-align:left;">

.03–.1–.28
</td>

<td style="text-align:left;">

.05–.2–.4
</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Vowel
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.2–.5–.9</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.33–.7–.98</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.27–.7–.97</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.16–.4–.69</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.04–.2–.42</span>
</td>

<td style="text-align:left;">

.39–.6–.84
</td>

<td style="text-align:left;">

.01–0–.09
</td>

<td style="text-align:left;">

.05–.3–.57
</td>

<td style="text-align:left;">

.15–.3–.7
</td>

</tr>

</tbody>

</table>

### Local, non-normalized

Here, I show the mutual information (shared entropy) of each pair of
features in bits (rounded to two decimal places). This is calculated
independently within each piece/movement, and the
`minimum`–`mean`–`maximum` is shown.

#### Cocopops

<table class="table" style="color: black; margin-left: auto; margin-right: auto;">

<thead>

<tr>

<th style="text-align:left;">

</th>

<th style="text-align:left;">

Contour
</th>

<th style="text-align:left;">

Melodic interval
</th>

<th style="text-align:left;">

Scale degree
</th>

<th style="text-align:left;">

Duration
</th>

<th style="text-align:left;">

Procedes rest
</th>

<th style="text-align:left;">

Position in word
</th>

<th style="text-align:left;">

Melisma
</th>

<th style="text-align:left;">

Capitalized
</th>

<th style="text-align:left;">

Punctuation
</th>

</tr>

</thead>

<tbody>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Melodic interval
</td>

<td style="text-align:left;">

3–5–5.7
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Scale degree
</td>

<td style="text-align:left;">

2.9–4.5–5.3
</td>

<td style="text-align:left;">

3.5–5.7–6.7
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Duration
</td>

<td style="text-align:left;">

1–2.8–4.3
</td>

<td style="text-align:left;">

1.3–3.7–5.3
</td>

<td style="text-align:left;">

1.1–3.5–5.2
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Procedes rest
</td>

<td style="text-align:left;">

.1–1.4–2.5
</td>

<td style="text-align:left;">

.1–1.4–2.5
</td>

<td style="text-align:left;">

.1–1.4–2.6
</td>

<td style="text-align:left;">

.1–1.4–2.6
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Position in word
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.8–2.3–3.4</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.9–3.1–4.4</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.9–2.9–4.1</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.2–2.1–3.5</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1–1.1–2.2</span>
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Melisma
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–.1–.2</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–.1–.2</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–.1–.2</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–.1–.2</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–0–.1</span>
</td>

<td style="text-align:left;">

0–.1–.2
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Capitalized
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.2–.8–1.9</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.2–1.2–2.2</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.2–1.1–2.1</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1–.7–1.9</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–.2–1.4</span>
</td>

<td style="text-align:left;">

.1–.6–1.4
</td>

<td style="text-align:left;">

0–.1–.2
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Punctuation
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–.3–1.9</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–.5–2.4</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–.4–2.4</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–.3–1.6</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–.1–1</span>
</td>

<td style="text-align:left;">

0–.3–1.4
</td>

<td style="text-align:left;">

0–.1–.2
</td>

<td style="text-align:left;">

0–.2–1.1
</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Vowel
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">1.4–3.8–4.7</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">1.4–5.1–6.2</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">1.4–4.7–5.9</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">1.3–3.3–4.7</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1–1–2.4</span>
</td>

<td style="text-align:left;">

1–3.1–4.3
</td>

<td style="text-align:left;">

0–.1–.2
</td>

<td style="text-align:left;">

.2–1.2–2.3
</td>

<td style="text-align:left;">

0–.5–2
</td>

</tr>

</tbody>

</table>

#### Handel

<table class="table" style="color: black; margin-left: auto; margin-right: auto;">

<thead>

<tr>

<th style="text-align:left;">

</th>

<th style="text-align:left;">

Contour
</th>

<th style="text-align:left;">

Melodic interval
</th>

<th style="text-align:left;">

Scale degree
</th>

<th style="text-align:left;">

Duration
</th>

<th style="text-align:left;">

Procedes rest
</th>

<th style="text-align:left;">

Position in word
</th>

<th style="text-align:left;">

Melisma
</th>

<th style="text-align:left;">

Capitalized
</th>

<th style="text-align:left;">

Punctuation
</th>

</tr>

</thead>

<tbody>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Melodic interval
</td>

<td style="text-align:left;">

0–4.8–5.6
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Scale degree
</td>

<td style="text-align:left;">

0–4.3–5.2
</td>

<td style="text-align:left;">

0–5.7–6.9
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Duration
</td>

<td style="text-align:left;">

0–2.3–3.7
</td>

<td style="text-align:left;">

0–3.1–4.7
</td>

<td style="text-align:left;">

0–2.9–4.6
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Procedes rest
</td>

<td style="text-align:left;">

0–1.5–2.4
</td>

<td style="text-align:left;">

0–1.7–2.5
</td>

<td style="text-align:left;">

0–1.5–2.5
</td>

<td style="text-align:left;">

0–1.1–3.1
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Position in word
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–2–3.4</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–2.8–3.8</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–2.7–3.8</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–1.4–2.9</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–.8–2.1</span>
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Melisma
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–.2–.8</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–.2–.8</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–.2–.8</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–.2–.8</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–.2–.8</span>
</td>

<td style="text-align:left;">

0–.2–.8
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Capitalized
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–.7–2.2</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–.9–2.3</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–.8–2.2</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–.5–1.9</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–.4–1.4</span>
</td>

<td style="text-align:left;">

0–.5–1.5
</td>

<td style="text-align:left;">

0–.2–.8
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Punctuation
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–1.3–2.9</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–1.8–3</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–1.7–2.9</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–1.1–2.7</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–.9–2.2</span>
</td>

<td style="text-align:left;">

0–.9–2.2
</td>

<td style="text-align:left;">

0–.2–.8
</td>

<td style="text-align:left;">

0–.4–1.3
</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Vowel
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–3.7–5.2</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–4.9–6.4</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–4.7–6.6</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–2.6–4.2</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–1.5–2.6</span>
</td>

<td style="text-align:left;">

0–2.9–3.8
</td>

<td style="text-align:left;">

0–.2–.8
</td>

<td style="text-align:left;">

0–.9–2.3
</td>

<td style="text-align:left;">

0–1.7–3
</td>

</tr>

</tbody>

</table>

#### Bach

<table class="table" style="color: black; margin-left: auto; margin-right: auto;">

<thead>

<tr>

<th style="text-align:left;">

</th>

<th style="text-align:left;">

Contour
</th>

<th style="text-align:left;">

Melodic interval
</th>

<th style="text-align:left;">

Scale degree
</th>

<th style="text-align:left;">

Duration
</th>

<th style="text-align:left;">

Procedes rest
</th>

<th style="text-align:left;">

Position in word
</th>

<th style="text-align:left;">

Melisma
</th>

<th style="text-align:left;">

Capitalized
</th>

<th style="text-align:left;">

Punctuation
</th>

</tr>

</thead>

<tbody>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Melodic interval
</td>

<td style="text-align:left;">

3.2–4.8–5.5
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Scale degree
</td>

<td style="text-align:left;">

1.7–4.4–5.2
</td>

<td style="text-align:left;">

2.5–6.2–7.6
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Duration
</td>

<td style="text-align:left;">

.6–2–3.6
</td>

<td style="text-align:left;">

1.3–3.2–4.7
</td>

<td style="text-align:left;">

1.2–3.1–4.6
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Procedes rest
</td>

<td style="text-align:left;">

.2–1.2–2.4
</td>

<td style="text-align:left;">

.2–1.4–2.6
</td>

<td style="text-align:left;">

.2–1.3–2.7
</td>

<td style="text-align:left;">

.2–.9–2.5
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Position in word
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.7–1.9–3.5</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">1.6–3.2–4.4</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">1.3–3.1–4.2</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.5–1.3–2.9</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.2–.7–1.4</span>
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Melisma
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–.2–.4</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–.2–.4</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–.2–.4</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–.2–.4</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0–.2–.4</span>
</td>

<td style="text-align:left;">

.1–.2–.4
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Capitalized
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1–1–2.4</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1–1.8–2.5</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1–1.7–2.6</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1–.7–1.7</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1–.3–1</span>
</td>

<td style="text-align:left;">

.1–.9–1.7
</td>

<td style="text-align:left;">

.1–.2–.4
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Punctuation
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.4–1.2–2</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.6–1.8–2.8</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.5–1.7–2.7</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.3–.9–1.6</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.2–.8–1.8</span>
</td>

<td style="text-align:left;">

.4–1–1.7
</td>

<td style="text-align:left;">

.1–.2–.4
</td>

<td style="text-align:left;">

.1–.5–1.3
</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Vowel
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">1.4–3.5–5.1</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">2.6–5.1–6.4</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">2.3–4.9–6.3</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.8–2.5–3.6</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.2–1.2–2.1</span>
</td>

<td style="text-align:left;">

1.7–3.2–4.8
</td>

<td style="text-align:left;">

.1–.2–.4
</td>

<td style="text-align:left;">

.1–1.7–2.6
</td>

<td style="text-align:left;">

.9–1.7–2.8
</td>

</tr>

</tbody>

</table>

### Global, normalized

Here, I show the mutual information (shared entropy) of each pair of
features as a proportion of the joint entropy (rounded to two decimal
places). This is calculated across the whole corpus.

#### Cocopops

<table class="table" style="color: black; margin-left: auto; margin-right: auto;">

<thead>

<tr>

<th style="text-align:left;">

</th>

<th style="text-align:left;">

Contour
</th>

<th style="text-align:left;">

Melodic interval
</th>

<th style="text-align:left;">

Scale degree
</th>

<th style="text-align:left;">

Duration
</th>

<th style="text-align:left;">

Procedes rest
</th>

<th style="text-align:left;">

Position in word
</th>

<th style="text-align:left;">

Melisma
</th>

<th style="text-align:left;">

Capitalized
</th>

<th style="text-align:left;">

Punctuation
</th>

</tr>

</thead>

<tbody>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Melodic interval
</td>

<td style="text-align:left;">

.6
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Scale degree
</td>

<td style="text-align:left;">

.38
</td>

<td style="text-align:left;">

.59
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Duration
</td>

<td style="text-align:left;">

.18
</td>

<td style="text-align:left;">

.2
</td>

<td style="text-align:left;">

.18
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Procedes rest
</td>

<td style="text-align:left;">

.27
</td>

<td style="text-align:left;">

.16
</td>

<td style="text-align:left;">

.18
</td>

<td style="text-align:left;">

.29
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Position in word
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.14</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.15</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.13</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.14</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.2</span>
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Melisma
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.01</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.01</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.01</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.02</span>
</td>

<td style="text-align:left;">

.02
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Capitalized
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.03</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.05</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.03</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.03</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.04</span>
</td>

<td style="text-align:left;">

.07
</td>

<td style="text-align:left;">

.04
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Punctuation
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.02</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.03</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.02</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.02</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.03</span>
</td>

<td style="text-align:left;">

.03
</td>

<td style="text-align:left;">

.09
</td>

<td style="text-align:left;">

.04
</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Vowel
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.24</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.2</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.11</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.05</span>
</td>

<td style="text-align:left;">

.14
</td>

<td style="text-align:left;">

.01
</td>

<td style="text-align:left;">

.04
</td>

<td style="text-align:left;">

.03
</td>

</tr>

</tbody>

</table>

#### Handel

<table class="table" style="color: black; margin-left: auto; margin-right: auto;">

<thead>

<tr>

<th style="text-align:left;">

</th>

<th style="text-align:left;">

Contour
</th>

<th style="text-align:left;">

Melodic interval
</th>

<th style="text-align:left;">

Scale degree
</th>

<th style="text-align:left;">

Duration
</th>

<th style="text-align:left;">

Procedes rest
</th>

<th style="text-align:left;">

Position in word
</th>

<th style="text-align:left;">

Melisma
</th>

<th style="text-align:left;">

Capitalized
</th>

<th style="text-align:left;">

Punctuation
</th>

</tr>

</thead>

<tbody>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Melodic interval
</td>

<td style="text-align:left;">

.58
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Scale degree
</td>

<td style="text-align:left;">

.22
</td>

<td style="text-align:left;">

.45
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Duration
</td>

<td style="text-align:left;">

.08
</td>

<td style="text-align:left;">

.15
</td>

<td style="text-align:left;">

.09
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Procedes rest
</td>

<td style="text-align:left;">

.19
</td>

<td style="text-align:left;">

.13
</td>

<td style="text-align:left;">

.04
</td>

<td style="text-align:left;">

.1
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Position in word
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.05</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.09</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.04</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.04</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.08</span>
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Melisma
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.02</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.01</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.01</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.03</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.07</span>
</td>

<td style="text-align:left;">

.04
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Capitalized
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.03</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.03</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.02</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.03</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.07</span>
</td>

<td style="text-align:left;">

.05
</td>

<td style="text-align:left;">

.13
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Punctuation
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.08</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.09</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.04</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.08</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.22</span>
</td>

<td style="text-align:left;">

.08
</td>

<td style="text-align:left;">

.06
</td>

<td style="text-align:left;">

.08
</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Vowel
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.11</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.29</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.22</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.12</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.05</span>
</td>

<td style="text-align:left;">

.11
</td>

<td style="text-align:left;">

.01
</td>

<td style="text-align:left;">

.04
</td>

<td style="text-align:left;">

.07
</td>

</tr>

</tbody>

</table>

#### Bach

<table class="table" style="color: black; margin-left: auto; margin-right: auto;">

<thead>

<tr>

<th style="text-align:left;">

</th>

<th style="text-align:left;">

Contour
</th>

<th style="text-align:left;">

Melodic interval
</th>

<th style="text-align:left;">

Scale degree
</th>

<th style="text-align:left;">

Duration
</th>

<th style="text-align:left;">

Procedes rest
</th>

<th style="text-align:left;">

Position in word
</th>

<th style="text-align:left;">

Melisma
</th>

<th style="text-align:left;">

Capitalized
</th>

<th style="text-align:left;">

Punctuation
</th>

</tr>

</thead>

<tbody>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Melodic interval
</td>

<td style="text-align:left;">

.51
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Scale degree
</td>

<td style="text-align:left;">

.19
</td>

<td style="text-align:left;">

.46
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Duration
</td>

<td style="text-align:left;">

.08
</td>

<td style="text-align:left;">

.16
</td>

<td style="text-align:left;">

.12
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Procedes rest
</td>

<td style="text-align:left;">

.19
</td>

<td style="text-align:left;">

.12
</td>

<td style="text-align:left;">

.07
</td>

<td style="text-align:left;">

.15
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Position in word
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.06</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.06</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.06</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1</span>
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Melisma
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.02</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.01</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.01</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.02</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.07</span>
</td>

<td style="text-align:left;">

.03
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Capitalized
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.02</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.04</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.03</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.03</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.04</span>
</td>

<td style="text-align:left;">

.09
</td>

<td style="text-align:left;">

.07
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Punctuation
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.05</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.07</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.04</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.05</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.14</span>
</td>

<td style="text-align:left;">

.1
</td>

<td style="text-align:left;">

.07
</td>

<td style="text-align:left;">

.06
</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Vowel
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.07</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.25</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.18</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.09</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.05</span>
</td>

<td style="text-align:left;">

.15
</td>

<td style="text-align:left;">

.02
</td>

<td style="text-align:left;">

.06
</td>

<td style="text-align:left;">

.06
</td>

</tr>

</tbody>

</table>

### Global, non-normalized

Here, I show the mutual information (shared entropy) of each pair of
features in bits (rounded to two decimal places). This is calculated
across the whole corpus.

#### Cocopops

<table class="table" style="color: black; margin-left: auto; margin-right: auto;">

<thead>

<tr>

<th style="text-align:left;">

</th>

<th style="text-align:left;">

Contour
</th>

<th style="text-align:left;">

Melodic interval
</th>

<th style="text-align:left;">

Scale degree
</th>

<th style="text-align:left;">

Duration
</th>

<th style="text-align:left;">

Procedes rest
</th>

<th style="text-align:left;">

Position in word
</th>

<th style="text-align:left;">

Melisma
</th>

<th style="text-align:left;">

Capitalized
</th>

<th style="text-align:left;">

Punctuation
</th>

</tr>

</thead>

<tbody>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Melodic interval
</td>

<td style="text-align:left;">

5.7
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Scale degree
</td>

<td style="text-align:left;">

4
</td>

<td style="text-align:left;">

6.8
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Duration
</td>

<td style="text-align:left;">

1.7
</td>

<td style="text-align:left;">

2.5
</td>

<td style="text-align:left;">

2.2
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Procedes rest
</td>

<td style="text-align:left;">

1.5
</td>

<td style="text-align:left;">

1.5
</td>

<td style="text-align:left;">

1.6
</td>

<td style="text-align:left;">

1.6
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Position in word
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">1.2</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">1.8</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">1.5</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">1.2</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">1</span>
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Melisma
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">0</span>
</td>

<td style="text-align:left;">

.1
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Capitalized
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.2</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.5</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.3</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.2</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1</span>
</td>

<td style="text-align:left;">

.4
</td>

<td style="text-align:left;">

.1
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Punctuation
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.3</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.2</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1</span>
</td>

<td style="text-align:left;">

.2
</td>

<td style="text-align:left;">

.1
</td>

<td style="text-align:left;">

.1
</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Vowel
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">1.3</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">3.5</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">2.9</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">1.4</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.5</span>
</td>

<td style="text-align:left;">

1.6
</td>

<td style="text-align:left;">

.1
</td>

<td style="text-align:left;">

.4
</td>

<td style="text-align:left;">

.2
</td>

</tr>

</tbody>

</table>

#### Handel

<table class="table" style="color: black; margin-left: auto; margin-right: auto;">

<thead>

<tr>

<th style="text-align:left;">

</th>

<th style="text-align:left;">

Contour
</th>

<th style="text-align:left;">

Melodic interval
</th>

<th style="text-align:left;">

Scale degree
</th>

<th style="text-align:left;">

Duration
</th>

<th style="text-align:left;">

Procedes rest
</th>

<th style="text-align:left;">

Position in word
</th>

<th style="text-align:left;">

Melisma
</th>

<th style="text-align:left;">

Capitalized
</th>

<th style="text-align:left;">

Punctuation
</th>

</tr>

</thead>

<tbody>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Melodic interval
</td>

<td style="text-align:left;">

5.7
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Scale degree
</td>

<td style="text-align:left;">

2.6
</td>

<td style="text-align:left;">

5.9
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Duration
</td>

<td style="text-align:left;">

.7
</td>

<td style="text-align:left;">

1.8
</td>

<td style="text-align:left;">

1.1
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Procedes rest
</td>

<td style="text-align:left;">

1.2
</td>

<td style="text-align:left;">

1.3
</td>

<td style="text-align:left;">

.4
</td>

<td style="text-align:left;">

.6
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Position in word
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.5</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">1.1</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.5</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.3</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.4</span>
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Melisma
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1</span>
</td>

<td style="text-align:left;">

.1
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Capitalized
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.2</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.4</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.2</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.2</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.2</span>
</td>

<td style="text-align:left;">

.2
</td>

<td style="text-align:left;">

.1
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Punctuation
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.6</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">1</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.5</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.5</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.7</span>
</td>

<td style="text-align:left;">

.4
</td>

<td style="text-align:left;">

.1
</td>

<td style="text-align:left;">

.2
</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Vowel
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">1.4</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">4.2</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">3.3</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">1.5</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.5</span>
</td>

<td style="text-align:left;">

1.3
</td>

<td style="text-align:left;">

.1
</td>

<td style="text-align:left;">

.4
</td>

<td style="text-align:left;">

.8
</td>

</tr>

</tbody>

</table>

#### Bach

<table class="table" style="color: black; margin-left: auto; margin-right: auto;">

<thead>

<tr>

<th style="text-align:left;">

</th>

<th style="text-align:left;">

Contour
</th>

<th style="text-align:left;">

Melodic interval
</th>

<th style="text-align:left;">

Scale degree
</th>

<th style="text-align:left;">

Duration
</th>

<th style="text-align:left;">

Procedes rest
</th>

<th style="text-align:left;">

Position in word
</th>

<th style="text-align:left;">

Melisma
</th>

<th style="text-align:left;">

Capitalized
</th>

<th style="text-align:left;">

Punctuation
</th>

</tr>

</thead>

<tbody>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Melodic interval
</td>

<td style="text-align:left;">

5.4
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Scale degree
</td>

<td style="text-align:left;">

2.4
</td>

<td style="text-align:left;">

6.4
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Duration
</td>

<td style="text-align:left;">

.8
</td>

<td style="text-align:left;">

2.2
</td>

<td style="text-align:left;">

1.5
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Procedes rest
</td>

<td style="text-align:left;">

1.2
</td>

<td style="text-align:left;">

1.3
</td>

<td style="text-align:left;">

.8
</td>

<td style="text-align:left;">

.9
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Position in word
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.5</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">1.4</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.8</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.5</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.5</span>
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Melisma
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1</span>
</td>

<td style="text-align:left;">

.1
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Capitalized
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.2</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.5</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.3</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.2</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.1</span>
</td>

<td style="text-align:left;">

.5
</td>

<td style="text-align:left;">

.1
</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Punctuation
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.4</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.8</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.5</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.4</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.5</span>
</td>

<td style="text-align:left;">

.6
</td>

<td style="text-align:left;">

.1
</td>

<td style="text-align:left;">

.2
</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;font-weight: bold;background-color: white !important;">

Vowel
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.8</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">3.8</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">2.8</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">1</span>
</td>

<td style="text-align:left;">

<span style=" font-weight: bold;    color: darkblue !important;">.4</span>
</td>

<td style="text-align:left;">

1.6
</td>

<td style="text-align:left;">

.1
</td>

<td style="text-align:left;">

.5
</td>

<td style="text-align:left;">

.5
</td>

</tr>

</tbody>

</table>
