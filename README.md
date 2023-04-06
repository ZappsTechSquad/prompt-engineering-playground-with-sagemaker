## Prompt Engineering

"Prompt engineering” refers to efforts to extract accurate, consistent, and fair outputs from large generative models, such text-to-image synthesizers or large language models (LLMs). LLMs are trained on large-scale bodies of text, so they encode a great deal of factual information about the world. But they’re trained to produce sequences of words that are probable in the general case — not accurate in the particular case.

What is a prompt?
- Text given to a pre-trained model for a prediction task

Components of Prompt
- Context
- Task (Instruction, question etc.)
- Image/Text
- Training samples 
- Generative Model

### Types of Prompt Engineering

1. Several types of prompt engineering include:
   1. Zero shot
   2. One shot and Few shot
   3. Chain of thought
4. Advanced concepts on prompt engineering
5. Adversarial Prompt engineering

#### 1. Zero Shot:
Zero-shot prompting enables a model to make predictions about previously unseen data without the need for any additional training. 

This is in contrast to traditional machine learning techniques, which require a large amount of labeled training data to make accurate predictions. 

In the context of prompt engineering, zero-shot learning can be used to generate natural language text without the need for explicit programming or pre-defined templates. 


#### 2. One Shot and Few Shot Prompting:

One-shot prompting is used to generate natural language text with a limited amount of input data such as a single example or template. 

One-shot prompting can be combined with other natural language processing techniques like dialogue management and context modeling to create more sophisticated and effective text generation systems. 

Few-shot prompting is a technique where the model is given a small number of examples, typically between two and five, in order to quickly adapt to new examples of previously seen objects. 

Few-shot learning can be used in the context of prompt engineering, to create natural language text with a limited amount of input data. Although it requires less data, this technique can allow for the creation of more versatile and adaptive text generation models.

By using advanced techniques such as few-shot prompting, it is possible to create natural language generation models that are more flexible, adaptable, and engaging for human users.

### Chain of thought prompting

Chain-of-thought (CoT) prompting improves the reasoning ability of LLMs by prompting them to generate a series of intermediate steps that lead to the final answer of a multi-step problem.


In this lab, we are going to uncover how to setup SageMaker Studio for prompt engineering utility and use cases with different types of prompt engineering techniques. 

## Setup - UI
- Navigate to `SageMaker Studio`.
- Click on `Home` on the left panel.
- Deploy a model and capture the endpoint name and model parameters which the model accepts. 
- Now that our endpoint is created (which can also be seen in SageMaker-Studio dashboard), navigate to `prompt-engineering-playground-with-sagemaker
` folder that you cloned. Note: Create an empty folder with name `templates` inside `prompt-engineering-playground-with-sagemaker
` folder.

- Check the instructions for creating GUI within the environment using Streamlit present in `start_playground.txt` file. In order to launch the GUI, click on `File` within SageMaker Studio tab, then click on `New` and navigate to `Terminal`.
  - Within the Terminal, run the following command: `pip install boto3 streamlit streamlit-ace -Uq`
  - Create an empty `templates` folder within `amazon-sagemaker-generativeai` folder before launching the app.
  - Next, run the next command found in start_playground.txt -- `streamlit run invoke_endpoint.py`. Make sure you are in the right directory to run this command in the terminal (`amazon-sagemaker-generativeai/studio-playground-ui/`). Once the command is executed, you can view your Streamlit app in your browser.
  - Copy the URL for SageMaker Studio and update the same by appending `/proxy/<port_no>`. You would have received the port number after running the Streamlit app. Domain URL should look similar to `https://d-lcxav5wg2gdg.studio.us-east-1.sagemaker.aws/jupyter/default/proxy/8502/`
  - Once you open the domain link, you can update the json with your model details such as `endpoint_name` and `model parameters` including the ranges.
  > 📝 The the data type for the range should be the same as default parameter for e.g. if the default value is in `float` then the range values should be in `float` as well. 
  
  ![image](/images/streamlitapp.png)
  
  - Click on `Apply (CMD+Enter)`. Once executed, you should be able to see the endpoint reflected on the left pane with the model parameters that can be tuned as a configuration knob while running prompt engineering.
  
  ![image](/images/flanmodel.png)
  
- Now we can get started with the model playground and run prompt engineering on the deployed model endpoint within our environment in a secured fashion.


## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.

