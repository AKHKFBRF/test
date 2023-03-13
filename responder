import streamlit as st
import openai

# Set up the OpenAI API key and model name
openai.api_key = "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"
model_name = "curie:ft-personal-2023-03-12-06-42-12"

# Create a form to get user inputs
with st.form(key='my_form'):
    st.write('## Rapid Response Generator')
    st.write('Please enter your prompt')
    prompt = st.text_area('Prompt', '')

    st.write('Prompt:', prompt)

    # Make the completion request
    completion = openai.Completion.create(
        model=model_name,
        prompt=prompt,
        n=3,
        temperature=0.75,
        top_p=0.75,
        presence_penalty=0.5,
        frequency_penalty=0.5,
        max_tokens=150,
        stop=["\n", "END"]
    )

    # Display the top 3 responses
    st.write('## Top Responses')
    for i, choice in enumerate(completion.choices):
        st.write(f'{i + 1}. {choice.text.strip()}')

    submit_button = st.form_submit_button(label='Submit')
