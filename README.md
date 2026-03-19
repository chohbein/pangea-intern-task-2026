# Pangea Chat: Gen AI Intern Task (Summer 2026)

- Altered feedback.py to work with claude api. Had to reformat the response to fit the json format. See 'feedback tool' and 'tools/tool choice'. Looks like it returns correct json schema.

- test_feedback_integration.py: altered to work with Anthropic API key. import dotenv, etc.

- test_schema.py: specified utf-8 encoding (windows issue) return json.loads((EXAMPLES_DIR / "sample_inputs.json").read_text(encoding='utf-8'))

- test_feedback_unit.py: edited to fit anthropic API use. 


While making tests, i realized the fundamental issue of this project is getting the model to pick up on what the user is intending to say: As errors increase, it becomes harder for the LLM to identify and correct what the user was intending to say.
