# Deep Value Benchmark

## Conceptual Overview
![conceptual overview](blah)


## Cite


## Datasets

Here is the [full dataset](https://www.dropbox.com/scl/fi/dhqqsc1c9q86cxpcq0r0s/dvb_all_prompts_full.json?rlkey=z0zpuakaqw7bra2lhg38bpjf5&st=2q0fauk5&dl=0) of 12k prompts. 

Here is a [downsample](https://www.dropbox.com/scl/fi/4akhk9vxug1p748itz9un/dvb_extra_prompts_1k_sample.json?rlkey=3xhky9blvl1kqpl05z0iayqxd&st=mblci4lt&dl=0) of 1k prompts for quicker experimentation. We made this because the full dataset is quite big 
(in terms of questions and input tokens). However, this should be big enough for most research questions. We chose this 
sample size to give 95\% power for an exact two-tailed binomial test, assuming an effect size of Cohen's g 
(i.e., difference from chance) of 0.05, to determine if the DVGR differs from chance (0.5) at a significance level of 0.05. 


## Dataset Structure

### Core Columns

**prompt_id** (string)
- Unique identifier for each prompt

**prompt** (string)
- The full prompt text containing training examples followed by a test question
- Training examples establish a pattern of shallow preferences
- Test question creates conflict between shallow preference and deep value

**expected_deep_value_choice** (string)
- Values: `"Option A"` or `"Option B"`
- This indicates if the model generalized the deep value or not

### Value Definitions

**deep_values** (dict)
Contains information about the fundamental value being tested:
- `preferred`: Name of the deep value (e.g., "justice", "fairness")
- `less_preferred`: Name of the contrasting deep value (e.g., "self_improvement")
- `preferred_definition`: Explanation of what the preferred value means for an AI agent
- `less_preferred_definition`: Explanation of what the less preferred value means for an AI agent

**shallow_preferences** (dict)
Contains information about the surface-level preference:
- `preferred`: Name of the shallow preference (e.g., "Formal Language")
- `less_preferred`: Name of the contrasting preference (e.g., "Colloquial Language")
- `preferred_definition`: Description of the preferred shallow preference
- `less_preferred_definition`: Description of the less preferred shallow preference

**context** (dict)
Domain and activity information:
- `name`: The domain (e.g., "communication")
- `activity`: The specific activity within that domain (e.g., "establishing and maintaining interpersonal relationships")

