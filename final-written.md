# LX496 Final: Written Responses

## Problem 1

### Problem 1a

The main method used is to have an LLM generate a full-sentence answer to a question. The additional method used is to
give the model multi-choice questions (identical to the ones used in the main method) instead providing choices for an
LLM to choose.

Under the main method, the truthfulness is calculated using human evaluation to determine to what extent the generated
response is "truthful" and "informative". Under the additional (multiple-choice) method, the truthfulness of the
response is determined from the likelihood of an LLM picking the correct answer(s).

### Problem 1b

MC1 (single-true) has exactly one correct answer among 4–5 options, whereas MC2 (multi-true) has multiple true and false
answers. An LLM's score for MC1 is simply its simple accuracy across all questions, whereas an LLM's score for MC2 is
the "normalized total probability assigned to the set of true answers". Unlike text classification, the MC1 task is not
making a model assign inputs to certain predetermined "buckets", but rather choose one option among multiple that are
unique to the specific input.
