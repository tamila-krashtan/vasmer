# Vasmer's Etymological Dictionary

This is a database containing the articles of the Russian edition of Vasmer's Etymological Dictionary based on the version commonly found on the web. This revision includes corrections of distortions caused by OCR and other minor enhancements. Additionally, it contains a list of abbreviations, for the one found in the paper version is far from being exhaustive.

## Sources

Initial data was taken from the [StarLing database](https://starling.rinet.ru/cgi-bin/response.cgi?root=%2fusr%2flocal%2fshare%2fstarling%2fmorpho&morpho=1&basename=morpho\vasmer\vasmer&first=1&off=&text_word=&method_word=substring&ic_word=on&text_general=&method_general=substring&ic_general=on&text_origin=&method_origin=substring&ic_origin=on&text_trubachev=&method_trubachev=substring&ic_trubachev=on&text_editorial=&method_editorial=substring&ic_editorial=on&text_pages=&method_pages=substring&ic_pages=on&text_any=&method_any=substring&sort=word&ic_any=on&encoding=utf-eng). Additionally were consulted both German and [Russian](http://www.slovorod.ru/etym-vasmer/) editions of the dictionary.

## Contents and structure

The repository contains two databases:
1. Articles from the Russian edition of Vasmer's dictionary.
2. List of abbreviations used in the dictionary.

Article structure was generally retained with the addition of `forms` field:
* `word`: headword of the article;
* `forms`: alternative and grammatical forms of the word as well as words of the same root given in bold at the beginning of the article;
* `general`: main text up to the first `||` delimiter;
* `origin`: main text after the first `||` delimiter;
* `trubachev`: notes by Oleg Trubachyov, each enclosed in square brackets. Places where these notes apply are marked in `general` and `origin` with `[Т]`;
* `editorial`: notes by the editor, each enclosed in square brackets. Places where these notes apply are marked in `general` and `origin` with `[Р]`;
* `pages`: volume and page(s) in the Russian edition of the dictionary where the article is located.

Note:
* Fields `general` and `origin` occasionally contain unattributed annotations in square brackets (e.g. in *волыня́ки*).
* Several articles contain two `||` delimiters, thus consisting of three parts. In such cases, the second and third part of the article both are contained in `origin` field (e.g. in *бобр*).
* Only the words in bold at the very beginning of the article were included in `forms` (see, for example, *и́рей*: *и́рий* is included, *и́рья* isn't). 

Abbreviation database fields:
* `abbreviation`: the abbreviation as it (mostly) appears in the dictionary;
* `aliases`: comma-delimited variants of the same abbreviation and other abbreviations applying to the same term;
* `type`: one of the following types of the term abbreviated:
    * `language`: languages as well as dialects and language families;
    * `russian dialect`: dialects of Russian;
    * `meta`: etymology and navigation;
    * `pos`: parts of speech;
    * `grammar`: other grammatical concepts;
    * `misc`: other common abbreviations;
* `meaning_ru`: the meaning of the abbreviation in Russian;
* `meaning_en`: the meaning of the abbreviation in English;
* `lang_code`: ISO code of the language if exists (this field is always blank if `type` is not `language`).

Note:
* Different terms may be referred to by different abbreviations (e.g. *дат.* may refer either to *дательный (падеж)* 'dative (case)' or to *датский* 'Danish').
* There exist abbreviations consisting of several parts, each already included in the list. In such cases, the ones used often (e.g. *др.-чеш.* for Old Czech) are included in the list, while the rare ones (e.g. *стар.-тур.* for Old Turkish) aren't.
* Contractions (e.g. *сущ-ных* for *существительных*) were not included in this list.

## What has been done

* Added contents to articles where they were missing (e.g. for *ма́рля*).
* Separated pairs of articles which were 'glued' together (e.g. *гам* and *гамаза́*).
* Corrected typos listed at the end of the 4th volume.
* Corrected article names consisting of two words: the second word was originally parsed as a part of the article body (e.g. *хо́дором ходи́ть*).
* Added missing opening/closing brackets – some were absent in the original text, some were lost in the process of OCR.
* Moved Trubachyov's notes to the appropriate column if they were fully or partially left in the main text (e.g. for *ела́нь*, *ковш*).
* Corrected punctuation where it was OCRed wrongly (e.g. *укр.. блр.* -> *укр., блр.* at *ёвня*).
* Corrected italicization of words in Cyrillic script (e.g. `<i>вла̑ч</i>и<i>̑</i>м` -> `<i>вла̑чи̑м</i>`).
* Corrected some wrongly displayed characters (Russian ё, Ukrainian ї, Polish ł, etc.).
* Replaced characters from wrong scripts (Cyrillic *р* and *а* in *раndа*, Latin *rpe* in *rpeч*, etc.).
* Removed hyphenation and spaces in words which were torn apart by line breaks (e.g. *ниже-  гор.* at *алы́р*).
* Corrected occasional OCR 'typos' (e.g. *мож(ж)све́льник* -> *мож(ж)еве́льник*).
* Changed Latin characters to Cyrillic in headwords.

Note:
* HTML syntax present in the articles: `<i>` for italic, `<sup>` for superscript, `&gt;` for >, `&lt;` for <.
* It's highly likely that there can still be found a lot of wrong characters (especially in the Greek text), typos and wrong punctuation. Pointing out any of them would be highly appreciated.