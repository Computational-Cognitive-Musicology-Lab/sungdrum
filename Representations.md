# Humdrum Representations of Lyrics

In this document I define new standard for representing lyrical and linguistic data in humdrum format.
I also propose a specific set of guidelines for these representations.

### Classic representations

The original humdrum user guide defines three representations for lyrics ([here](https://www.humdrum.org/guide/ch27/)):

+ `**text` --- word level
+ `**silbe` --- syllable level
+ `**IPA` --- phoneme level


The `**text` and `**silbe` representations are used in many humdrum datasets.
Unfortunately, most of these datasets don't follow the original specification: in particular, punctuation is rarely separated from text (as the spec says it should be) and `_` is often used for melismatic notes instead of `|`.
Instead, annotators have used these representations like generic lyric-in-score representations, as they might in a notation software.
Thus, the representations---in theory and in practice---run into the [problems and inconsistencies]() typical of lyric notation.


### New representations

To better represent lyric data and *linguistic* data, I propose five new exclusive interpretations.
Continuing the theme established by Huron, I use German terms:

+ Basic encoding
  + `**liedtext` (lyrics)
  + `**ipa` (Internationales Phonetisches Alphabet---e.g., pronunciation)
+ Analytical annotations
  + `**reim` (rhyme)
  + `**wortart` (part of speech)
  + `**dependenz` (syntax)
  
The first two are closely modeled on `**silbe`/`**text`/`**IPA`, while the later are entirely new to humdrum.

---

I also propose several tandem interpretations, to refine the representation and analysis/interpretation of lyric data.
Several tandem interpretations are relevant in all of my exclusive interpretations:

+ `*silbe` | `*wort` | `*wort-` | `*wort[n]` | `*lemma`
  + Indicates if each token represents a syllable or word.
+ `*verbatim` | `*canonical` | `*transcrip` | `*auto`
  + Indicates the provenance of the data: 
    + *verbatim* encoding of score;
    + *canonical* lyrics of piece/song;
    + *transcription* of specific recording or performance;
    + *automatic* transcription from audio recording.
+ `*S...`
  + S is for "Sprache" (language).
  + Indication of language/dialect.
    + Use the [ISO 639-3](https://en.wikipedia.org/wiki/ISO_639-3) language code, 
      + ISO 639-3 codes can be accessed [here](https://iso639-3.sil.org/code_tables/download_tables)---the table, accessed on 2025-10-09, is also included in this repository, in the file `LanguageCodes_ISO639-3.tsv`.
      + In keeping with [IEFT standards](https://en.wikipedia.org/wiki/IETF_language_tag) additional dialect/regional information can be included as well:
        + [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country codes.
        + [UN M49](https://en.wikipedia.org/wiki/UN_M49) region codes.
        + Anything else needed.
    + **Form**:
      + `*S` + ISO 639-3 (+ `-` + optional dialect indication)
    + **Examples**:
        + `*Seng-US` (American English)
        + `*Seng-GB` (UK English)
        + `*Sdeu` (German)
        + `*Sibo-NG` (Nigerian Igbo)
        + `*Sdan` (Danish)
        + `*Sesp-419` (Latin-American Spanish)
        + `*Sesp-MX` (Mexican Spanish)
        + `*Szho` (general Chinese)
  


## **liedtext

> The `**liedtext` interpretation is closely modeled on the classic `**silbe` and `**text` representations, but using `*silbe` and `*wort` as tandem interpretations to distinguish syllabic and word-level representations respectively.
> Still, to keep everything in one place, I fully define them both here, without reference to the older interpretations.

The `**liedtext` represents the lyrics---the words of the music, understood as abstract lexical categories.
This means that `**liedtext` does not represent pronounciation.
Rather, the appropriate canonical, "dictionary" spelling of all words should be used---this makes it easier to aggregate and compare words across pieces and corpora.
This also includes contractions, which should be written in full form: `don't` = `do_not`. 
(This avoids confusion with possessive markers, for example in a word like `somebody's`---`somebody_is` versus `somebody's` (possesive).)

> If you wish to indicated dialectical pronounciations that are not "standard"---for example, `runnin' with the devil`---you can provide a 
> sprach interpretation like `*Seng-US-southern` or, better yet, indicate pronunciation explicitely in an `**ipa` spine.
> Writing "`runnin'`" should only be valid `**liedtext` if you are doing `*verbatim` copying of a score/text.

----

Interpretation of `**liedtext` data depends on the `**silbe`/`**wort`/etc. tandem interpretation:

+ When `*wort` is in effect, each token represents an entire word.
  For multi-syllable words, the word should be placed to align with the record where the first syllable occurs---for multi-syllable words, later syllables in the word are marked with the melsima marker `|`.
  If multiple words are pronounced in a single word, or otherwise need to be recorded on one record, they should be separated by `_`, not spaces.
  If `*wort-` is in effect, `-` is placed between syllables of words.
+ When `*wort[]` is in effect, each token represents an entire word.
  However, unlike `**wort`, in multi-syllable words the whole word is repeated for each syllable, but followed by `[n]` enumerating the syllable number.
+ When `*silbe` is in effect, each token represents a syllable.
  For multi-syllable words, `-` must be placed at the begining and/or end of tokens, to indicate in-word connections.
    + `-` at the end of a token indicates that the next syllable belongs to the same word.
    + `-` at the beginning of a token indicates that the previous syllable belongs to the same word.
    + `-` may also occur at the start and end of a token.
    + For hyphenated words put a tilde (`~`) at the connection point, similar to a hyphen connecting syllables.
    
If fully encoded, `**silbe`, `**wort-`, and `**wort[n]` tokens are fully interchangebale with no loss of information.
In contrast, `**wort` and `**lemma` discard some information (syllable boundary information)
    
    
```
**kern	**liedtext	**liedtext	**liedtext	**liedtext	**liedtext
*	*silbe	*wort	*wort-	*wort[n]	*lemma
*M4/4	*	*	*	*	*
2F#	looks	looks	looks	looks	look
2F#	like 	like	like	like	like
=	=	=	=	=	=
4E	earth-	earthquakes	earth-quakes	earthquakes[1]	earthquake
4D	|	|	|	|	|
4E	-quakes	-	-	earthquakes[2]	-
8D	and	and	and	and	and
4F#	light-	lightning	light-ning	lightning[1]	lightning
4.D	-ning	-	-	-	-
*-	*-	*-	*-	*-
```

#### Syllabification

The process of breaking words into *orthographic* syllables is somewhat arbitrary, balancing morphological (meaningful) and phonemic/phonetic considerations.
(This is especially so in languages where orthography and pronunciation are not consistently related.)
Since syllable pronunciation can and should be reliably encoded in `**ipa`, syllabification in `**liedtext` spines should focus on morphology---grouping together the most recognizable meaningful units, with less regard to pronunciation.
However, general syllabification---especially for unseen words (slang or proper nouns) is not a solved problem. 
The best we can do is aim for consistency.


#### Capitalization

Capitalization is used in various ways in the orthographies of different languages.
Worse, it is often used for multiple purposes: in English, for example, capitalization marks "proper" nouns *and* the beginning of sentences.
Such mixed uses should be avoided, as a capitalized "The" at the beginning of a sentence is not really different from a "the" later in the sentence.

Capitalization should be used consistently for one purpose, where the capitalization is *consistently* meaningful.
For example, the word "prudence" is a general noun, while "Prudence" is the name of person.
Thus, in English `**liedtext`, we capitalization should be reserved only for proper nouns---syntactic units (i.e., sentences) can be indicated separately.
The word "I," which is normally always capitalized, should not be capitalized (to avoid conflict with potential abbreviations.)

When writing `**liedtext` in other languages, the capitalization norms of that language can be respected, but the aim should be to stay true to the distinction above:
if a word is, by its nature, always capitalized, that is fine.
If a word is sometimes capitalized, and other times not, that distinction should be meaningful and consistent.
If capitalization is used to indicate multiple, independent types of information, then an alternative approach to encoding that information should be sought.


#### Multi-word tokens

Sometimes, multiple words act together as a single meaningful unit.
This is most obvious in proper names (e.g., first and last).
In these cases, words can be connected using the `~` marker, treated similar to `-` connecting syllables.

#### Punctuation

Punctuation is also used in various ways in the orthographies of different languages.
Worse, it is often used for multiple purposes: in English, for example, punctuation is used to indicate some syntactic boundaries, but also lists of nouns, asides, acronyms, and abbreviations.
Such mixed uses should be avoided.
Punctuation, should be used to represent one unambiguous piece of information.

I recommend avoiding uses of punctuation for acronyms or abbreviations. 

+ Acronyms should simply appear as capital letters, with no periods. Each capital letter is equivalent to a word, and they should be connected by `~` because they act like mutli-word units.
  + `A~K~A`
+ Abbreviations should be spelled out:
  + `et cetera` instead of "etc."
  + `versus` (instead of "vs.")
  + `mister` (instead of "Mr."), `doctor` (instead of `Dr.`)


Though punctuation is used to represent syntactic units, to some extent, in many orthographies, these syntactic annotations are generally not self consistent, nor consistent with proper syntactic analysis.
Thus, in `**liedtext` we use *only* the period (`.`) and question mark (`?`), and only to make mark complete syntactic closure---marking out separate syntactic units.
This may at times mean something close to "complete" sentences; however, lyrics often include syntactic structures that are not "complete."
It is tempting to attempt to use `,`, `;`, or `:` to indicate other subsyntactic groupings, but syntax is very complex, and it is best to instead use an independent syntactic analysis (see `**dependenz`, below).

---

One final case to consider is quotations.
Quotations in lyrics may be indicated as usual using `"`.
For hierarchical quotations, use increasing numbers of `"` to mark nested quotes---i.e., `""`, `"""`, `""""`.

```
**liedtext
and
Doc-
-tor~
~Dre
said
"Slim~
~Shady
you_are
a
base_
_head.
Man
you
wast-
-ed
*-
```


#### Numbers

Numbers should be spelled out using characters: e.g., "one hundred and ninety nine."


#### Vocables

Vocable (nonsense) syllables should be spelled in whatever way seems most natural, but marked with `^`, so they can easily be filtered out.
For the purpose of syntactic grouping (with the period), vocables interspersed into otherwise syntactic utterances should be ignored.


### Summary of **liedtext

`**liedtext` token elements:

+ `a-z` used to write words.
+ `A-Z` used as 
  + Initial letter of word, indicating proper nouns;
  + Single letters, indicating a letter acting as a word, as in an acronym, or something like `mister~T`.
+ `-` used to indicate syllables which connect to form words.
+ `_` used to separate words written on a single record.
+ `~` use to indicate multi-word units.
+ `|` used to indicate melismatic syllables.
+ `.` used to mark syntactic closure.
+ `?` used to mark syntactic closure in question form.
" `'` used only to represent possessive case.




### **ipa

This interpretation represents the pronunciation of syllables/words using the [International Phonetic Alphabet](https://en.wikipedia.org/wiki/International_Phonetic_Alphabet) (IPA).
Since the IPA represents phonemes, it is important to include a language indicator (e.g., `*Seng-US`).
This is because different languages distinguish different phoneme categories, which influences the IPA interpretation.
Tokens in `**ipa` may be syllabic (most common) or lexical, and should be marked as such using `*silbe` or `*wort`.

Tokens in `**ipa` may be encoded directly in unicode, or using one of the various [ASCII transliterations](https://en.wikipedia.org/wiki/Comparison_of_ASCII_encodings_of_the_International_Phonetic_Alphabet).
For example, the original humdrum `**IPA` specification calls for a modified form of the [Kirshenbaum ASCII-IPA](https://en.wikipedia.org/wiki/Usenet_ASCII-IPA_transcription) scheme.
The scheme being used should be indicated with a tandem interpretation, starting with either `*unicode` or `*ascii-x` where x is a scheme name: such as `*ascii-Kirshenbaum`.
(Note that since, humdrum disallows use of `*` and `!` at the start of data fields, transliterations involving these characters must be modified.
In `*ascii-Kirschenbaum` we use `+` in place or `*`.)

As an example, below I list the phonemes suitable for representing general American English dialects in the unicode and Kirshenbaum transliteration.
(Some English dialects will require more vowel distinctions.)

*Unicode*  *Kirshenbaum*  *Example word*
---------- -------------- ---------------
p          p              **p**it
b          b              **b**it
t          t              **t**ip
d          d              **d**o 
k          k              **c**at
ɡ          g              **g**o
m          m              **m**at
n          n              **n**o
ŋ          N              ri**ng**
ɾ          + (not *)      bu**tt**er
f          f              **f**at
v          v              **v**at
θ          T              **th**in
ð          D              **th**is
s          s              **s**it
z          z              **z**oo
ʃ          S              **sh**oe
ʒ          Z              sei**z**ure
h          h              **h**at
ɹ          r              **r**ot
j          j              **y**es
l          l              **l**eft
w          w              **w**hat
i          i              b**ea**t
ɛ          E              b**e**t
ɑ          A              b**o**t
ɔ          O              b**oa*t
o          o              b**oa*t
u          u              b**oo**t
y          y              **y**es
ʌ          V              b**u**ck
ɪ          I              b**i**t
ʊ          U              p**u**t
ə          @              **a** car
æ          &              b**a**t
ɚ          R              b**urr**


Accents are indicated with `'` (primary accent) and `,` (secondary accent) placed at the beginning of accented tokens.
Note that, though "accents" are clearest within multi-syllable words, single syllable words may also be accented (or not), within a whole utterance.


Humdrum example:

```
**liedtext	**ipa	**ipa
*silbe	*silbe	*silbe
*	*unicode	*ascii-Kirshenbaum
i	'aI	'aI
see	'si	'si
a	ə	@
bad	'bæd	'b&d
moon	'mun	'mun
a-	ə	@
-ris-	'raI	'raI
-ing	zIn	zIn
*-	*-	*-
```
 

# New Analytical Representations


## Rhyme

The `**reim` interpretation indicates where rhymes occur in a lyric.
A `**reim` spine should be paired with a `**liedtext` spine.
Groups of syllables/words in the lyrics which rhyme with each other are indicated with arbitrary codes in the `**reim` spine.
The arbitrary codes are usually simply `A`, `B`, `C`, etc., with uppercase letters used for stressed syllables and lowercase letters (`a`, `b`, `c`) used for unstressed syllables,
However, any arbitrary code(s) can be used.
If more than one successive (or proximal) syllables/words rhyme, they may be grouped together using parentheses, to indicate that they are perceived as a single, multi-syllable rhyme.


Example:

```
**liedtext	**riem
*Seng-US	*Seng-US
*silbe	*silbe
to	.
all	.
the	.
la-	A
-dies	.
in	.
the	.
place	A
with	.
style	.
and	.
grace	A
allow	.
me	.
to	.
lace	A
these	.
lyr-	.
-i-	.
-cal	.
douche-	(B
-s	b)
in	.
your	.
bush-	(B
-es	b)
*-	*-
```

> For many complex examples, see the [Musical Corpus of Flow](https://github.com/Computational-Cognitive-Musicology-Lab/MCFlow) dataset.




### Part-of-Speech tags

The `**wortart` spine represents [part-of-speech](https://en.wikipedia.org/wiki/Part_of_speech) (POS) information for words in an associated `**liedtext` spine.
"Parts of speech" include categories like verb, noun, and adjective.
We recommend using the categories from the [Universal Dependencies](https://universaldependencies.org/u/pos/index.html) project:

+ [NOUN](https://universaldependencies.org/u/pos/NOUN.html): noun
+ [VERB](https://universaldependencies.org/u/pos/VERB.html): verb
+ [ADJ](https://universaldependencies.org/u/pos/ADJ.html): adjective
+ [ADP](https://universaldependencies.org/u/pos/ADP.html): adposition (including prepositions)
+ [ADV](https://universaldependencies.org/u/pos/ADV.html): adverb
+ [AUX](https://universaldependencies.org/u/pos/AUX.html): auxiliary
+ [DET](https://universaldependencies.org/u/pos/DET.html): determiner
+ [PART](https://universaldependencesi.org/u/pos/PART.html): particle
+ [PRON](https://universaldependencies.org/u/pos/PRON.html): pronoun
+ [PROPN](https://universaldependencies.org/u/pos/PROPN.html): proper noun
+ [CCONJ](https://universaldependencies.org/u/pos/CCONJ.html): coordinating conjunction
+ [SCONJ](https://universaldependencies.org/u/pos/SCONJ.html): subordinating conjunction
+ [INTJ](https://universaldependencies.org/u/pos/INTJ.html): interjection
+ [X](https://universaldependencies.org/u/pos/X.html): other

POS tags are associated with words; If paired with a syllabic (`*silbe`) representation, the tag should be aligned with the first syllable in each word.

```
**liedtext	**wortart
*Seng-US	*Seng-US
*silbe	*
i	PRON
see	VERB
a	DET
bad	ADJ
moon	NOUN
a-	VERB
-ris-	.
-ing	.
*-	*-
```


### Dependency grammar

The `**dependenz` interpretation represents syntactic relationships in an associated `**liedtext` spine.
Dependency tags are associated with words; If paired with a syllabic (`*silbe`) representation, the tag should be aligned with the first syllable in each word.

Within an independent syntactic utterence (i.e., a sentence), one word serves as the *root*, marked `ROOT`.
All other words are related by a dependency relationship to another word, or the root.
Each dependent word has a "head" word, on which it depends.

Dependencies are indicated with `>` (dependent on later word) and `<` (dependent on earlier word) markers.
If the immediately next/pr word is the head, then the `<`/`>` arrows are used alone.
If the head is not the immediately next/previous word, the word itself must be stated after the `<`/`>`.
If more than word instance of the same head word, multiple arrows can be stacked to point to a later/earlier word.
For example, `>>run` would mean that the current word is dependent not on the *second* following instance of the word "run."


The `arrow>word` notation is sufficient to indicate where dependencies occur.
We may also include the type of the dependency before the arrow.
We use the categories from the [Universal Dependencies](https://universaldependencies.org/u/dep/index.html) project.

```
**liedtext	**dependenz
*silbe	*
i	nsubj>
see	ROOT
a	det>moon
bad	nmod>
moon	nsubj>
a-	ccomp<see
-ris-	.
-ing	.
=	=
i	nsubj>
see	ROOT
trou-	obj<
-ble	.
on	case>way
the	det>
way	nmod<trouble
```

The `**dependenz` tokens above correspond to this dependency tree:


```
i ---> see <------------arising     i ---> see <-- trouble
                  moon->|                                |<---------way 
             bad->|                                         on----->|
           a---- >|                                            the->|
```





