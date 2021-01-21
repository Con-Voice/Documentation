Con Voice - Novel approach to real time voice cloning, using a variety of approaches.

First gain a deeper understanding of the problem, then research three implementations of similar ideas(Text to Speech, Cocktail Party Problem, Voice Cloning), explain in detail their approach to the problem, solution architecture, flow of the data from start to finish, and their outcome.

Create and add to a glossary as I go along 

Keep a journal of milestones and setbacks, to refer to in later interviews

1.  Begin with notebooks for fast minimum viable product
- Start with notebooks to explore: 
	- Text to speech from recorded voice
	- Cocktail Party Problem
	- Voice Cloning 
- Voice and Audio Data Visualization Techniques
	- Fourier Transform, Fast Fourier
	- Spectrogram
	- Mel Spectrogram
	- Waveform Analysis
- Create Hypothesis for our approach after considering the approaches others have taken
- Iterate through variations in approach to the problem

[] TODO - Create a notebook within our version control system that contains an approach to solving the problem 

[] TODO - Create Link to the notebook, add here 



2.  From notebooks to organized scripts

-   When finished with basic development (on downsized datasets), 
-   Move code into scripts, reducing future tech debt
-   Create functions and classes for different parts of the pipeline (data, model, train, etc.) 
-   Break the pipeline into a sensible arrangement of functions and classes that form a cohesive overall approach
-   Train/Test split, model, preprocessing, fit, predict etc 


3.  Implement unit tests and logging

-   Log key events
-   Log training, and accuracy performance 
-   Log input and output during prediction
-   Add unit tests for the functions we wrote
-   Start with sanity checks, data type hints and error handling 
-   pick a test library, pytest or unittest, document why chosen and implement

4.  Experiment tracking and analysis

-   Implement [Weights and Biases](https://wandb.com/) (WandB) for tracking progress with our models 
-   Start with simple models
-   Slowly add complexity
-   Document the approach with readme files, articles cited 
-   Engineer with the intent to re-use components for later approaches and iterations
-   Track version numbers, and major revisions within version number
-   Document when changing the model, and how it resulted in improvements, call it version control success tracking
-   Hyperparameter tuning will take place when we have developed a method to document and record gains/losses or improvements

5.  Review and fine tune 

-   Does the model fits our use case, does the precision/recall or accuracy achieve acceptable performance? 
-   In the business use case does the models performance on new data justify the cost? Does it require additional data to succeed?
-   Compare logs on input data and performance to determine the breadth of training data. How does our model behave on data that is outside the scope, adversarial in nature?
-   What is the result of a prediction when calculated by hand? Test case to verify.
-   Write to logs or version control success tracking to compare the model’s output for a manual calculation and a predition
-   If a predicted class has a bad test performance, manually set threshold for determining class, if a test does well relax manually setting a threshold

6.  Wrap the model as an API so users can interact with it

-   Couple of components 
1. Voice capture and tune the model to nuance of captured voice 
	-   Create speech from text with a single pass/one or zero shot approach 
	
2.   Create a program that takes a users voice as input and applies a realtime style gan transfer(Voice Clone Over) of audio tone, pitch, cadence, and rythm of users voice with a voice that has been recorded or connected to 
	-  enable output of of con-voice, apply style of the recorded voice to clone or dub over users voice  
	
3. Flask/FastAPI implementation
	-   Modularize components, single vs batch predictions
	-   Make visual representation of the inner working available via the interactive website that allows a demo or experimental view of Con Voice
	-   Mel spectrogram representation of the two voices for comparison
	-   Allow access to Con Voice and hosted via AWS ?
	-   Dockerize it 
		-   Create docker image of our API to allow scaling for later use cases

7. Create an interactive frontend for your application.

-   Enable interactivity for users via web application, let others play with it to show off our work
-   Streamlit or Heroku to start possible merge to AWS if needed
-   Might be possible to run as an AWS Lambda Serverless Function if we can keep the model size and dependencies under 256MiB
