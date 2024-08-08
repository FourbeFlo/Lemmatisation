# Lemmatization
lemmatisation data for topic modelling research in 16th century Reformed exegesis texts for Paul's exegesis projet
* the abbreviations in the Bible in their standard form are those of the vulgate :
  - Latin : Biblia sacra : iuxta vulgatam versionem / recensuit et brevi apparatu critico instruxit Robertus Weber ; adiuvantibus B. Fischer, I. Gribomont, H. F. D. Sparks...[et al.]. Ed. quartam emendatam / praeparavit Roger Gryson ; cum socii B. Fischer, H. I. Frede, H. F. D. Sparks... [et al.], 1994

# Repository contents
* Corpus : training data for the language model and progression of their incorporation into the programme. On which texts we work.
* Lambertus_chap1-2 : the choosen texts in .txt
* dictionaries and abbreviations : dictionaries and abbreviations: list of words added to the vocabulary of the current language model, biblical abbreviation as used in Lambert's commentary.
* test : data for testing the accuracy of the language model on heterogeneous corpora (next octobre)
* file.tsv 
* questions.txt : personal notes on problems and choosen solutions

# problem and choices for lemmatization

List of problems seen during lemmatisation. this list serves as a personal reminder of the problems encountered.

1.  solved by the LASLA model.
  - enclytic particle _que, ue, ne_ 

2.  number : 
  - Arabic number: these are all the verse numbers not present in the LASLA model, but of no interest for a language model. 

3. abbreviation 
  - personnal name: 
    * D. T. Beza : Doctor, Theodorus Beza
    * reference authors : Eurip,  Euripidus; Crysosto, Crysostomus; August, Augustinus
    * reference books: Enchir, Enchiridon
    * 
  - dates :
    * Cal. kalendae 

  - technical vocabulary : 
    * epist. epistola
    * pag. pagina
    * quæst. quaestio 
    * vers. uersiculus
    * V uersiculus
    * versic uersiculus
    * etc be avare of the uariance inside the abbrevation system...

  - biblical books: 
    * follow the table in the abbreviations folder


4. 16th century texts: 
  - bilingual words (half greek-half latin scripture) : praxeωs cf. 2012897.png
  - the problem of capital letters
    the word are considered as NOMpro because of the capital letter in LASLA
    * Ecclesia, Episcopus, Auctor, Monacus

5. Printer's error
  in a few rare case some lettres are missing, it could be manually corrected for the lemmatization but not in the master file, because this is used for the OCR training. 
  - caneset for canescet

6. morphology: 

## possible solutions

* link the abbreviation with the full lemma, but there is still the problem of morphology. either don't fill in the information (empty) or choose the most likely case (often the ablative because it is a textual reference).

* I'm thinking of creating a POS for abbreviations
@abr.persnam : abbreviation of people's names
@abr.bib : abbreviation of biblical books
@abr.tech : technical abbreviation : papal verse etc...
=> if the morphology is not obvious, it is indicated as empty.

* make these step further with python : https://www.wisecube.ai/blog/named-entity-recognition-ner-with-python/
