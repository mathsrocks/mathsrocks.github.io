# fast.ai study note post \#0: why we need GPU(s) in Deep Learning

## Motivation
Mostly inspired by my thesis supervisor Peter S., I decided to dedicate a few off-work days to going through the [fast.ai](https://www.fast.ai/) course material. This is the 1st of the series of posts to record and share the learning throughout the journey. As a recovering perfectionist who used to flaunt his attention to detail (e.g. underlying theories) and unrealistic standards, the recent black swan events of varying scales such as COVID-19 and Kobe's death strike home for me: life is short and fragile. An integral part of the ancient Greek Philosophy Stocism is to live everyday as if it was the last in a non-mobid way. Allocating my time and attention to solving real-world problems is a big step toward living that philosophy that the fast.ai courses claim to share. 

## Initial thoughts
After sitting through a few hours of video for the first course, I can echo other people's view that [fast.ai](https://www.fast.ai/)'s courses are __practical__, which makes it rather appealing to me. For instance, each lession usually began with an array of high achieving students' past projects as a result of hardwork and talent. [Jeremy and Rachel](https://www.fast.ai/about/) have done a brillian job in terms of living up to fast.ai's slogan "Making neural nets uncool again". The best part is all the courses they offer are __free__.

## Bumpy road
Unexpectedly, the first bump I encountered while setting up the Google Cloud Platform (GCP) was the GPU quota. Needless to say, Google has changed its practice when it comes to GPU quota increase as my multiple requests all got rejected through canned emails. I even reached out to Google Cloud Sales Team as suggested but haven't received any meaningful response to date. After days of struggling and despite the USD300 free credit, I got to the point of almost giving up on GCP and looking for alternatives ("Constraints breed resourcefulness" - one of Amazon's Leadership Principles). Not to completely abandoning GCP, I re-configured and tweaked one of my existing GCE CPU-only instances where hard work had been put in to make Jupyter Lab work, and `pip`-installed the [fast.ai library](https://docs.fast.ai/install.html). Meanwhile, [Google Colab](https://colab.research.google.com/) still offers GPU as hardware accelerator when runing a notebook.

## Performance comparison: with vs. without a GPU
GCE instance (machine type: n1-standard-8 (8 vCPUs, 30 GB memory))
![GCE instance with CPU only](images/gce-cpu-only.png)

vs.

Google Colab with GPU
![GCE instance with hardware accelerator GPU on](images/colab-gpu.png)

GPU speeds up training the DL model by a considerable large margin, i.e. its training time each epoch is about 1/5 of the CPU-only counterpart.

## So what?
I have submitted another request to lift the GPU quota limit for the same GCP project used for comparison. If still not granted, I will spec up the current GCE instance and throw in more vCPUs to build up usage history to see what Google would come up then. 
