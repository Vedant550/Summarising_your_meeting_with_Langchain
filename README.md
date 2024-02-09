# Summarising_your_meeting_with_Langchain

Taking notes and summarizing meeting minutes are indispensable parts of daily business. Leveraging the transcripts exporting features of meeting software and contemporary Large language models, we can automate the boring work and allow us to spend more time on creative and interesting work. 

# Build the meeting summary script

-You need to import Langchain first.Then you need to set up an OpenAI API key.\n
-Then you can read the file and use CharacterTextSplitter to cut the raw text into small chunks. This would ensure each individual API call has less than 4k tokens from the input. This limit varies from model to model.\n
-Next, you are going to initialize a ChatGPT object and use it in load_summarize_chain . Each chunk of text is sent to ChatGPT to summarize independently. You are using prompt_template as a prompt template to generate the first chunk’s summary.\n
-For the following executions, the previous chunk’s summary and the prompt template refine_template will be combined as the prompt and sent to ChatGPT to summarise.\n
-This allows ChatGPT to summarise the current chunk while considering the previous context. This behavior is defined by the parameter type as refine in load_summarize_chain function.
