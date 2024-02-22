




A Data Analysis Report Analysing the Amazon Review Dataset: 		Collocation Extraction. 
 
 
Table of Content



INTRODUCTION……………………………………………………………………………………………………………..2




METHODS…………..………………………………………………………………………………………………………….3





E.D.A. & RESULT.…………………………………………………………………………………………………………….4





CONCLUSION………………………………………………………………………………………………………………….6





REFERENCES……………………………………………………………………………………………………………………7




















Introduction

As a member of Amazon’s Data Analysis team, the responsibility lies in analysing the languages utilized in positive customer reviews. This entails employing statistical modelling techniques such as co-occurrence frequency and mutual information to extract collocations.The Amazon positive review dataset is a tab separated file where each line corresponds to a different customer review. It consists of (Review_score, Product_id & Actual_review).The objective is to critically assess the outcomes, emphasizing the strengths and limitations of these selected methodologies.


Data Driven Questions

This report will use the results gotten from the analysis of the given dataset to provide answers to the following questions:
•	What are the advantages and limitations of the different collocation extraction algorithms used?
•	Which algorithm is more efficient in extracting collocations from the Amazon review dataset?








Methods

•	Data-Preprocessing (stopword and punctuation removal)

•	Part of speech tagging 

•	Co-occurrence frequency 

•	Pointwise mutual Information 




































Exploratory Data Analysis

In the pre-processing stage, essential NLTK libraries like pos_tag and word_tokenize were imported. The third column from the newly created file is initialized and tokenized. Tokenization, as highlighted by Jurafsky and Martin (2019), is crucial for extracting linguistic features like n-grams, part-of-speech tags, and syntactic dependencies. Following tokenization, part-of-speech tagging is applied, playing a vital role in syntactic parsing and aiding in understanding sentence structure (Allen, 1995). By assigning grammatical roles to words, POS tagging facilitates the comprehension of syntactic relationships within sentences, thus easing the parsing process. Lastly, bigrams are extracted along with their corresponding part-of-speech tags, as illustrated in Figure 2.



A second analysis was conducted, as depicted in Fig 2.1, using the co-occurrence frequency algorithm to examine the corpus. In this analysis, no filtering or preprocessing occurred. The results, as presented in Table 1, reveal that the bigrams consist mainly of word pairs lacking the characteristics of collocations. Manning and Schütze (1999) discussed in their book "Foundations of Statistical Natural Language Processing" that collocations exhibit restricted compositional properties. They elaborate that an expression in natural language is deemed compositional if its meaning can be inferred from the meanings of its individual components.


 


A third analysis was conducted on the same corpus, focusing on obtaining collocations. The method mirrored the previous analysis, but in this iteration, the co-occurrence algorithm was combined with part-of-speech (POS) tag filtering, stop word, and punctuation removal. Figure 2.2 illustrated how POS tag filtering eliminated non-phrase words, as demonstrated by Justeson and Katz (1995), enhancing bigram quality using combinations of adverbs, adjectives, and nouns. The table displays the top forty bigrams by frequency. Following the application of the POS filter, this output showed improvement over the previous algorithm, attributed to attention to syntactic relationships inherent in sentence structure—considerations absent in prior analyses where only bigrams with the highest frequency were returned. Can we assert that results from the co-occurrence frequency (with part-of-speech tags filter) truly represent strong collocations? Let's delve deeper into our analysis to ascertain.






The final analysis is conducted to extract collocations from the corpus using pointwise information. In this analysis, the individual probabilities P(x) and P(y), representing the likelihood of occurrence of each word independently, were considered along with the joint probability P(x,y) representing the likelihood of the word pair occurring together.(Manning and Schütze,1999).




Figure 2.4: Point wise frequency result visualization using word cloud. 



Conclusion 

The PMI (Pointwise Mutual Information) method is widely recognized and utilized, as evidenced by the work of past researchers like Church and Hank (1990), who highlighted its efficacy in word association. They contended that a reliable approach to discerning collocations is to attempt translation into another language; failure to do so indicates a likely collocation. However, it's worth noting that the PMI method is constrained by words of low frequency.

Examining the output of PMI analysis reveals compelling word pairs like "Mount Rushmore," "Esparante GTR-1," "Intel Celeron," "readme.txt," and "Mauna Kea," which serve as strong examples of collocation, aligning with Hank's assertion regarding translatable terms.
Additionally, co-occurrence analysis yields word pairs such as "memory card," "replay value," and "single player." However, the strength of these collocations compared to those identified through PMI analysis is debatable.

In conclusion, Pointwise analysis has its limitations and strengths. While it may not capture all nuances of collocation, it efficiently produces word pairs that are restricted by factors such as compositionality, non-modifiability, and un-substitutability. while co-occurrence analysis primarily emphasizes syntactic relationships (Justeson & Katz, 1995), it may also yield common word pairs as evidenced by its output in this analysis. 






















References 
1.	Allen, J. (1995). Natural language understanding. Benjamin-Cummings Publishing Company
2.	Church, K. W., & Hanks, P. (1990). Word Association Norms, Mutual Information, and Lexicography. Computational Linguistics, 16(1), 22–29
3.	Jurafsky, D., & Martin, J. H. (2019). Speech and language processing (3rd ed.). Pearson.
4.	Justeson, J. S., & Katz, S. M. (1995). Technical terminology: Some linguistic properties and an algorithm for identification in text." In Natural Language Engineering, 1(1), 9-27
5.	Kenneth Ward Church and Patrick Hanks. 1990. Word association norms, mutual information, and lexicography. Computational Linguistics, 16(1):22–29, March
6.	Manning, C., & Schütze, H. (1999). Foundations of Statistical Natural Language Processing (2nd ed.). MIT Press.

