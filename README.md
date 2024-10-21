<H3>NAME:Kavinraja D</H3>
<H3>REGISTER NO:212222240047</H3>
<H3>EX. NO.6</H3>
<H3>DATE:</H3>
<H1 ALIGN =CENTER>Implementation of Semantic ANalysis</H1>
<H3>Aim: to perform Parts of speech identification and Synonym using Natural Language Processing (NLP) techniques. </H3> 
 <BR>
<h3>Algorithm:</h3>
Step 1: Import the nltk library.<br>
Step 2: Download the 'punkt', 'wordnet', and 'averaged_perceptron_tagger' resources.<br>
Step 3:Accept user input for the text.<br>
Step 4:Tokenize the input text into words using the word_tokenize function.<br>
Step 5:Iterate through each word in the tokenized text.<br>
•	Perform part-of-speech tagging on the tokenized words using nltk.pos_tag.<br>
•	Print each word along with its corresponding part-of-speech tag.<br>
•	For each verb , iterate through its synsets (sets of synonyms) using wordnet.synsets(word).<br>
•	Extract synonyms and antonyms using lemma.name() and lemma.antonyms()[0].name() respectively.<br>
•	Print the unique sets of synonyms and antonyms.
<H3>Program:</H3>

```py
import nltk
from nltk.corpus import wordnet

# Download required NLTK resources
nltk.download('punkt')
nltk.download('averaged_perceptron_tagger')
nltk.download('wordnet')
nltk.download('punkt_tab')
nltk.download('averaged_perceptron_tagger_eng')

# Function to get synonyms of a word using WordNet
def get_synonyms(word):
    synonyms = set()
    for syn in wordnet.synsets(word):
        for lemma in syn.lemmas():
            synonyms.add(lemma.name())
    return synonyms

# Function to process a text file (optional usage)
def process_text_file(file_path):
    with open(file_path, 'r') as file:
        text = file.read()
    return text  # Return the processed text

# Input the text to analyze
text = input("Enter the text to analyze: ")

# Tokenize the text into sentences
sentences = nltk.sent_tokenize(text)

# Loop through each sentence
for sentence in sentences:
    # Tokenize each sentence into words
    words = nltk.word_tokenize(sentence)

    # Perform part-of-speech tagging
    pos_tags = nltk.pos_tag(words)

    # Extract verbs (POS tags starting with 'V' are verbs)
    verbs = [word for word, pos in pos_tags if pos.startswith('V')]

    # Get synonyms for each verb and print them
    for verb in verbs:
        synonyms = get_synonyms(verb)
        print(f"Verb: {verb}")
        print(f"Synonyms: {', '.join(synonyms) if synonyms else 'No synonyms found'}\n")

```

<H3>Output</H3>

![image](./Output/o1.png)


<H3>Result:</H3>
Thus ,the program to perform the Parts of Speech identification and Synonymis executed sucessfully.
