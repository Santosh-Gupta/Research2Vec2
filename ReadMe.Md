

<p align="center">
  <img src="https://snipboard.io/3kErQ6.jpg">
</p>

# Research2Vec2

This is an update to the original Research2Vec project at https://github.com/Santosh-Gupta/Research2Vec

When I first completed the project, I was only able to train 1,666,577 papers in computer science, and 2,096,359 papers from medline, with only an embedding size of 80 and 64 respectivly. 

I am able to train with much larger amounts of papers, and embedding size. This is due to in part of Google Colab upgrading their instances. This is also due to a library I made for instances of sparse training with RAM is limited, SpeedTorch [ https://github.com/Santosh-Gupta/SpeedTorch ] , with allows for fast CPU -> GPU transfer (100x faster than using Pytorch pinned CPU tensors), so that parameters not used in the training step can be stored on the CPU. 

I am now able to train 2,150,127 CS papers with the ideal embedding size of 512 (with SpeedTorch, it can handle much more than 512, but for similiarty there doesn't seem to be much advantage after 512) , and 14,886,544 papers from Medline with an embedding size of 188. Without SpeedTorch colab can only handle embedding sizes of around 96-100 before crashing. 

With SpeedTorch, I do not have any more computational limits for training decent sized embeddings for these papers, but now I do not have enough Google Drive space to contain all these embeddings, so unlike the first project, there are no embeddings readily availible to be downloaded and analyzed, but I provided the colab training notebooks so that others can train and perhaps store the embeddings. 

NOTE: If using colab, you'll need the version of the Colab notebook that has 25 gb of RAM, instead of the usual 12 gb. To get this type of instance, you need to crash your current instance due to overwhelming the RAM, and then a note in the bottom left corner asking if you would like to upgrade. You can do this by making a loop that keeps doubling the size of a numpy float matrix. 

Here is a direct lnk to the notebook, using SpeedTorch

https://colab.research.google.com/drive/1H0RNhz1jliW6gWmg5caaxbMiDcMZuJ-0

Here is a version of the notebook without SpeedTorch. In Colab, it can only handle about half the embedding size (94-96) without SpeedTorch. 

https://colab.research.google.com/drive/1jh7RUgeajhdWdGNfWG3Twm1ZjyTQU0KR

