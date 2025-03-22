# flowty-realtime-lcm-canvas

![example gif](example.gif)

### About
---

This is a real-time sketch to image demo using LCM and the [gradio library](https://github.com/gradio-app/gradio). 
If you're not familiar with LCM, read about it here - [article on Hugging Face](https://huggingface.co/blog/lcm_lora).

Thanks to LCM LoRA, you can also use different models by altering the model id in the ui.
The desired effect was for you to be able to draw on one side and see the changes at close to real-time on the other side.

Needless to say, this will perform worse on some GPUs, and better on some GPUs. 4090s usually perform best in the realtime scenario. Share your results!

This was tested on a macbook pro with M2 Max, 30 GPU - 32GB combo, python 3.10. Inference times were tolerable, about 1.2s per render. If you're getting good performance on your machine, feel free to tweak the parameters in order to get better results. You can also change the canvas size to 768 / 1024 in ui.py, depending on your model.

### Setup
---
* Setup a venv if you'd like to isolate your project environment: ```python -m venv env```
  * activate on MacOS: ```source ./env/bin/activate```
  * activate on Windows: ```env\Scripts\activate```
* Nvidia users should install PyTorch using this command: ```pip install torch --extra-index-url https://download.pytorch.org/whl/cu121```
* Install the requirements: ```pip install -r requirements.txt```
* Run ui.py: ```python ui.py```

After you run ui.py, models should be downloaded automatically to the models directory. It might take a few minutes depending on your network.
Once the models are downloaded, gradio will print to the console the url where you can access the ui.

### Use Google Colab
---
Google Colab users can also enjoy it by executing the following command and accessing the generated Gradio Public URL.  
(I think this is currently only available in the Colab Pro.)

```
!git clone https://github.com/flowtyone/flowty-realtime-lcm-canvas.git
%cd flowty-realtime-lcm-canvas
!pip install -r requirements.txt
!python ui.py --share
```

This is a community project from [flowt.ai](https://flowt.ai). If you like it, check us out!

<picture>
 <source media="(prefers-color-scheme: dark)" srcset="logo-dark.svg" height="50">
 <source media="(prefers-color-scheme: light)" srcset="logo.svg" height="50">
 <img alt="flowt.ai logo" src="flowt.png" height="50">
</picture>



💡 Programming Challenges for Flowty Realtime LCM Canvas
1️⃣ Custom Shape Rendering
📌 Challenge: Add support for drawing a custom shape (e.g., a pentagon or a star) on the canvas.
💡 Hint:

Add a button that, when clicked, draws the custom shape.

Use Path2D API in HTML5 Canvas for precise shape control.

Implement mouse events and Bezier curves to define shape points dynamically.

2️⃣ Real-time Collaboration Enhancement
📌 Challenge: Implement a history tracking system for real-time collaboration.
💡 Hint:

Store each action (like drawing a line or erasing a shape) in a history list.

Allow users to undo/redo changes.

Use WebSockets or IndexedDB to handle state management efficiently.

3️⃣ Dynamic Layer Management
📌 Challenge: Add a layer system to control the order of elements on the canvas.
💡 Hint:

Create a panel displaying a list of layers.

Enable drag & drop functionality to reorder layers.

Simulate z-index behavior for better layer control.