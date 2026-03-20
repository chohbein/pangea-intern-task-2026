# Pangea Chat: Gen AI Intern Task (Summer 2026)

- Altered feedback.py to work with claude api. Had to reformat the response to fit the json format. See 'feedback tool' and 'tools/tool choice'. Looks like it returns correct json schema.

- test_feedback_integration.py: altered to work with Anthropic API key. import dotenv, etc.

- test_schema.py: specified utf-8 encoding (windows issue) return json.loads((EXAMPLES_DIR / "sample_inputs.json").read_text(encoding='utf-8'))

- test_feedback_unit.py: edited to fit anthropic API use. 


While making tests, i realized the fundamental issue of this project is getting the model to pick up on what the user is intending to say: As errors increase, it becomes harder for the LLM to identify and correct what the user was intending to say.
  - This is hard to address in test cases. Try adding new rule to best address the ambiguous intended meaning in high error density sentences.
  - I considered adding a rule to the prompt such that it must use the provided target language to translate the input; this would potentially help in this rare case of users inputting linguistically-ambiguous erroneous sentences.
    - I decided against this; the case is more rare than the case where the user just accidently puts the wrong target language. Tradeoff.
