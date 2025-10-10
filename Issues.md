# Trails and Tribulations of lyric data


For vocal music, lyrics are often encoded in common music notation scores.
As is generally the case, lyrics in scores are intended as performance guides, not systematic encodings of musical information for research purposes.
Many computational musicology datasets include lyric data, encoded *ad hoc* in a form roughly equivalent score representations.
Massive amounts of lyric data can also be found online on various lyric websites, but with a *high* degree of inconsistency in formatting and accuracy.

In general, lyric data contains a wealth of information, beyond "just" the words.

+ Pronunciation information.
+ Rhyme information.
+ Stress and accent information.
+ Phrasing information.
+ Etc.

However, this information is not always consistently encoded, either between or within datasets.
Consider two different encodings of a famous lyric---*can you spot the differences?*:

+ 1a. `I see a bad moon a ri-sin'`
+ 2a. `I see trou-ble on the way`

+ 1b. `I see, the Bad Moon a-ris-ing`
+ 2b. `I see, troub-le on the way.`


What do the commas in the `b` examples refer to? 
Punctuation like this is often used *ad hoc* to represent musical/prosodic/syntactic units.
Why is Bad Moon capitalized? Should it be?
*Lyric data often features these sorts of inconsistencies from piece-to-piece, and line-to-line.*


---

What about lyric data is "unsystematic"?

+ Identifying provenance:
  + Where did the lyric come from? The composer/librettist? Album liner notes? Transcribed by ear?
+ Relies on regular language orthography, which may or may not map to pronunciation to various degrees.
+ Syllable stress not explicit.
+ Use of capitalization is not consistent.
+ Use of punctuation is not consistent.
  + What does a "," or a "!" in a lyric mean?
+ Treatment of multi-word lexical items.
+ Treatment of nonsense syllables (vocables).
+ Treatment of slang, or dialectical variations.




# Encoding Recommendations and (Towards) Proposed Standards


The following can be considered *recommendations for the creation and/or curation of song datasets*---and in parallel, as *warnings of potential pitfalls for when analyzing lyric data*.

More detailed recommendations, encoding schemes, and analysis scripts are posted in my `sungdrum` repository.
Currently, `sungdrum` is focused on English language, but the principles are broadly applicable.

<!--I assume here that the goal is *analysis*: if the goal is verbatim preservation---for example, of lyrics as encoded in a specific score edition---these recommendations may not apply.-->

### Lyric provenance

The provenence of lyrics should be considered and encoded in metadata.
Distinguish the follwing (sub)categories:

+ **Canonical lyrics** --- Associated with a *piece*
  + *Authorial*: Explicitly indicated by composer/lyricist
    + A priori (in performance score or libretto) 
    + Post hoc (liner notes, Genius "verified" annotations)
  + *Documented*:  Independently recorded by listeners or scholars
    + e.g., Crowd-sourced websites (pop music) or Ethnographic interviews (folk song)
+ **Transcribed lyrics** --- Associated with a *performance/recording*
  + *Aural*: By ear
  + *Mechanical*: By machine

The possibility of ambiguity or disagreement about lyrics is present in *all* forms, and must be considered.

### Decoupled Encoding

It is ideal to decouple independent aspects of lyrics/sung language.

+ **Distinguish orthographic information from pronunciation information.**
  + For pronunciation, International Phonetic Alphabet (IPA).
  + For word encoding, use canonical (dictionary) spellings.
    + Indicate dialect through IPA or metadata: `because` never `'cause` or `coz`.
  + Syllable boundaries should be at least consistent, and better yet systematic, but not based on pronunciation.
+ **Distinguish prosodic grouping information from syntactic grouping**.
  + Omit punctuation, or use only for full stops.
  + Do not use capitalization to indicate syntactic groupings.

