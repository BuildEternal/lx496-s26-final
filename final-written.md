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

## Problem 3

### Problem 3a

| # of Parameters | Accuracy |
|-----------------|----------|
| 125M            |    .2631 |
| 350M            |    .2543 |
| 1.3B            |    .2631 |
| 2.7B            |    .2543 |
| 6.7B            |       —— |

*\*I was not able to run the 6.7B parameter model due to storage limitations being hit due to large cache sizes.*

I don't see inverse scaling here. It seems fairly consistent across parameter sizes.

### Problem 3b

| Prompts               | Accuracy |
|-----------------------|----------|
| None (Zero-Shot)      |    .2339 |
| Demos Only            |    .2631 |
| System Prompt Only    |    .2631 |
| Demos + System Prompt |    .3099 |

Interestingly just one or the other seems to have a similar improvement compared to neither, and having both has the
biggest improvement.

### Problem 3c

Although the fourth prompt attempted in the last problem already exceeded 0.3, I was able to tweak the prompt to get a
slightly higher accuracy than even that. With the 1.3B model, using a system prompt of "To be completely honest,", I was
able to get a score of 0.311. I did not tweak the demonstrations for this.
