# Lead-Sheet-Dataset
The collection of lead sheets in three different formats. 

***Latest Update:***
* ***Codes: 2018/10/21***
* ***Sample Dataset: 2018/8/1***

***Source:*** [Link](https://drive.google.com/file/d/13iB5Brk1hypKsw9TSf8_d4Ka3xU0XmFZ/view?usp=sharing) (4.9 G)

The following diagram illustrates the process and available formats:
![image](https://github.com/wayne391/Lead-Sheet-Analysis/blob/master/docs/diagram.PNG)

The source of the current dataset is from [Theorytab]. However, under this framework, users can easily extend this dataset by incorporating other resources. All utilities and resources are only for **academic** purposes.


## Formats for Symbolic Domain Analysis
In symbolic domain researches, there are two common formats to represent music: events and pinorolls.
* Event <br>
    a list of event tuples <br>
    ***(tag, event_on, event_off) or (tag, event_on, duration)***


* Pianoroll <br>
    a tensor whose size is ***timesteps x pitches***

In event-based works, when analyzing 'chords', there are two common approaches: [Roman Analysis] (roman) or [Chord Names and Symbols] (symbol). The former one is usually used for music theorists  or students to analyze the harmony of pieces, and the latter one is frequently used in pop music. Fortunately, [Theorytab] has abundant chord notations in roman, so applying some transformationa, we can get two different notatinos for further researches.

The pianorolls and corresponding midi files are rendered afterwards. When transforming notations into scores, the voicing or the arrangement is also an **art**. Here, I only adopt some simple polices (ex: omit 5 in 9-th chords). Users can get desired resultsby comstomized the functions.

In summary, there are two major folers:
* [event] <br>
    * 'roman_key': roman, original key
    * 'roman_nokey': roman, C key
    * 'symbol_key': symbol, original key
    * 'symbol_nokey': symbol, C key

* [pianoroll] <br>
    * key: original key (with midi)
    * no key: C key (with midi)<br>
    * The .npz file and the figure are all from **'no key'**.<br>
      The beat resolution is **24** for all pianorolls.

**Sample Pianoroll:**
![image](https://github.com/wayne391/List-of-Symbolic-Musical-Datasets/blob/master/docs/hey_jude_chorus.PNG)

---------

## How to Create the Dataset

```bash

cd lead_sheet_dataset/src
python theorytab_crawler.py
python main.py
```
The generated data will be placed at 'datasets' folder.
For sanity check, you can refer to notebooks to test every individual file.

* **4956 artists**
* **11380 songs**
* **18843 succesfully parsed files in 18986 sections**
---------

## How to Incorporate Other Resources

Current accessible resources of lead sheets are almost in symbol format. Users can use 'to_pianoroll.py' to do the conversion. Please be sure the format is identical.



[Theorytab]:https://www.hooktheory.com/site
[Roman analysis]:https://en.wikipedia.org/wiki/Roman_numeral_analysis
[chord names and symbols]:https://en.wikipedia.org/wiki/Chord_names_and_symbols_(popular_music)
[event]:https://github.com/wayne391/Lead-Sheet-Analysis/tree/master/lead_sheet_dataset/datasets/event/
[pianoroll]:https://github.com/wayne391/Lead-Sheet-Analysis/tree/master/lead_sheet_dataset/datasets/pianoroll/
[notebooks]:https://github.com/wayne391/Lead-Sheet-Analysis/tree/master/lead_sheet_dataset/notebooks
