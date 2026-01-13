
### Prompt

I want to build a simple Interactive Quiz App using Gradio in Python. Could you write the code for me? The quiz questions should be stored in a separate file. I want a web-based interface with a dropdown for the question, multiple-choice answers, and a button to check if the answer is correct. Then please explain each part of the code step by step, as if I'm a beginner. Also, show me how to deploy this app on Hugging Face Spaces.

The generated code uses the "old" gradio which uses static question dropdown - so replace the above prompt with:

I want to build a simple Interactive Quiz App using the current version of Gradio (version 5.32.1) in Python. Could you write the code for me? The quiz questions should be stored in a separate file. I want a web-based interface with a dropdown for the question, multiple-choice answers, and a button to check if the answer is correct. Then please explain each part of the code step by step, as if I'm a beginner. Also, show me how to deploy this app on Hugging Face Spaces.

Resulting code:

```python
import gradio as gr
import json

# Load quiz data from the JSON file
with open("quiz_data.json", "r") as file:
    quiz_data = json.load(file)

# Extract mappings for convenience
question_list = [q['question'] for q in quiz_data]
question_to_options = {q['question']: q['options'] for q in quiz_data}
question_to_answer = {q['question']: q['answer'] for q in quiz_data}

# Function to update options based on selected question
def update_options(question):
    return gr.update(choices=question_to_options[question], value=None)

# Function to check the selected answer
def check_answer(question, selected_option):
    correct_answer = question_to_answer[question]
    if selected_option == correct_answer:
        return f"✅ Correct! The answer is {correct_answer}."
    else:
        return f"❌ Incorrect. The correct answer is {correct_answer}."

# Build Gradio Interface
with gr.Blocks() as demo:
    gr.Markdown("## 📝 Interactive Quiz App")

    # Dropdown to select question
    question_dropdown = gr.Dropdown(label="Select a Question", choices=question_list, value=question_list[0])

    # Dropdown for answer options (updates dynamically)
    option_dropdown = gr.Dropdown(label="Select an Answer", choices=question_to_options[question_list[0]])

    # Button to check answer
    check_btn = gr.Button("Check Answer")

    # Textbox to show result
    result_box = gr.Textbox(label="Result")

    # Event to update answer options when question changes
    question_dropdown.change(fn=update_options, inputs=question_dropdown, outputs=option_dropdown)

    # Event to check answer when button is clicked
    check_btn.click(fn=check_answer, inputs=[question_dropdown, option_dropdown], outputs=result_box)

if __name__ == "__main__":
    demo.launch()

```



