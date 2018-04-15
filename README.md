# Quora_Duplicay_Detection
This is a beginner machine learning project in python to calculate the probability of similarity between questions on quora.

Name of the College/Institution: Bharati Vidyapeeth College of Engineering Pune

  Student Name:  Robin Redhu
  
  E-Mail ID: robinredhu38@gmail.com

Final result of probablity score is uploaded on google drive  link is below :
  https://drive.google.com/open?id=17RNTgNqTgajnwo-qrm8n5yiQhKxHNHWY



	1.Background
  
	Where else but Quora can a physicist help a chef with a math problem and get cooking tips in return? Quora is a place to gain 
  and share knowledge—about anything. It’s a platform to ask questions and connect with people who contribute 	unique insights 
  and quality answers. This empowers people to learn from each other and to better understand the world.
	Over 100 million people visit Quora every month, so it's no surprise that many people ask similarly worded questions.
  Multiple questions with the same intent can cause seekers to spend more time finding the best answer to their question,
  and make writers feel they need to answer multiple versions of the same question. Quora values canonical questions because 
  they provide a better experience to active seekers and writers, and offer more value to both of these groups in the long term.


  2.Our Understanding

  First of all for any text mining project text pre processing should be done first to understand the patterns and links between
  the attributes. After that I decided to tokkenize each sentence. As I can compare token of each questions with each other to find
  out the duplicay between the pairs. Now If it contains similar root words more than the value set then it will consider
  those questions as similar as not similar.
	
  
	3.	Scope
  
  This model can be used to predict the similarity between the sentences that have same root words.


  4.Out of Scope
  
  Sentences with synonym is difficult to be predicted using this model


	5.Assumptions
  
	In the following project I have assumed that if any of the question among question1 and question2 is a nan value then it will 
  give 1 as output.

	6.Solution Approach
  
  First of all the very first step was to clean the data to remove stopwords, numbers, punctuations and also to replace the
  abbreviation with the normal text. After that main method starts and here it goes,
  
	 To begin, we defined terms like:
	▪	tokens: a word, number, or other “discrete” unit of text.
	▪	stems: words that have had their “inflected” pieces removed based on simple rules, approximating their core meaning.
	▪	lemmas: words that have had their “inflected” pieces removed based on complex databases, providing accurate, context-aware meaning.
	▪	stopwords: low-information, repetitive, grammatical, or auxiliary words that are removed from a corpus before performing approximate matching.
	
	The method work by transforming or removing elements from input sequences, then comparing the output sequences for exact matches.  
  If any element of the sequence matches or their orders differ, then the match fails, and the sentences are not identified as equivalent.
  In order to locate more true positives, we need to relax our definition of equivalence.  The next most logical way to do this is to 
  swap our exact sequence matching with a set similarity measure.  One of the most common set similarity measures is the Jaccard similarity 
  index, which is based on the simple set operations union and intersection.

	We are comparing two sentences: A and B.  We represent each sentence as a set of tokens, stems, or lemmae, and then we 
  compare the two sets.  The larger their overlap, the higher the degree of similarity, ranging from 0% to 100%.  If we set 
  a threshold percentage or ratio, then we have a matching criterion to use.  Let’s walk through an example.
  Let’s say we define sentences to be equivalent if 50% or more of their tokens are equivalent.  Here are two sample sentences:
	▪	The young cat is hungry.
	▪	The cat is very hungry.
  When we parse these sentences to remove stopwords, we end up with the following two sets:
	▪	{young, cat, hungry}
	▪	{cat, very, hungry}
  The Jaccard index is composed of a numerator and denominator.  In the numerator, we count the number of items that are  
  shared between the sets.  In the denominator, we count the total number of items across both sets.  In our example above,
  our intersection is {cat, hungry}, which has count of two.  The union of the sets is {young, cat, very, hungry}, 
  which has a count of four.  Therefore, our Jaccard similarity index is two divided by four, or 50%.  
	
	However, in addition to just lemmatizing tokens, we are also going to ignore all lemmas that do not correspond to nouns. 
  The motivation here is that we care about the “things” in the sentence, not the “actions” in the sentence; as a result, 
  using only noun lemma sets will allow us to achieve more positive matches.


	
	7.Implementation Framework
  
	Main Mehtod - CASE-INSENSITIVE NOUN LEMMA SIMILARITY AFTER STOPWORD REMOVAL



	Hardware Details
  
  The MacBook Pro "Core i5" 2.5 13-Inch (Mid-2012/USB 3.0), 
  a 22 nm "Ivy Bridge" 2.5 GHz Intel "Core i5" processor (3210M), 
  with two independent processor "cores" on a single silicon chip, a 3 MB shared level 3 cache, 
  4 GB of 1600 MHz DDR3L SDRAM (PC3-12800) installed in pairs (two 2 GB modules), 
  a 500 GB HDD
  
  
	Software Details
  
  Anaconda Jupyter Notebook
