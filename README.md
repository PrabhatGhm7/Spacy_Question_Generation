# Question Generator

This script provides a function `generate_question(sentence)` that takes a sentence as input and generates a grammatically correct question based on its structure. It uses the spaCy library for natural language processing (NLP) to analyze the sentence and identify its various components (e.g., subject, verb, object, time, place, etc.) to form a valid question.

## Requirements

- Python 3.x
- spaCy library
- A spaCy language model (e.g., `en_core_web_sm`)

## Function Overview
generate_question(sentence)
This function processes an input sentence, identifies the components of the sentence, and generates a grammatically correct question based on its structure. It handles various sentence structures, including those involving location, time, reason, and manner.

How it Works
1. Input Sentence Parsing:
The sentence is processed using spaCy's NLP pipeline to extract grammatical components. The doc object, which represents the parsed sentence, is iterated through to identify different syntactic structures like subjects, verbs, objects, etc.

2. Component Identification:
The function identifies the following components:

Subject: The noun or pronoun performing the action.
Verb: The action or state of being (in its base form).
Object: The direct object of the action (e.g., the thing being acted upon).
Place: Locations or proper nouns related to the sentence (e.g., "New York").
Time: Temporal expressions (e.g., "today", "yesterday").
Reason: Cause-related phrases (e.g., "because", "due").
Manner: Descriptive adverbs (e.g., "quickly", "carefully").
Auxiliary Verb: Helping verbs (e.g., "is", "was", "has").
3. Question Formation:
Once the components are identified, the function determines the appropriate question word based on the sentence structure:

Where: For location-related questions.
When: For time-related questions.
What: For object-related questions.
Why: For reason-related questions.
How: For manner-related questions.
The function then generates a grammatically correct question using the correct form of the verb, considering tense and subject agreement.

4. Verb Handling:
If an auxiliary verb (is, was, etc.) is detected, it is used directly in the question.
If no auxiliary verb is found, the main verb is used in its base form.
The function handles past tense verbs by using "did" and adapts the verb based on the subject ("do", "does", "did").
5. Output:
The function returns a grammatically correct question. If the components required to form a question are missing, it returns an error message: "Can't Generate Question".

