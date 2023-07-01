# innopolis-global-ai-challenge-2023

Second place at kaggle on the task "Diagnosis of intracranial hemorrhages using unsupervised learning algorithms". The task was difficult, but interesting. It was necessary to train the model using only brain tomography images. It was impossible to use third-party images with masks, ready-made pre-trained models for such tasks, manual markup. 

Briefly about the solution:
1. Using OpenCV, highlighting areas by color, + additionally highlighting only areas inside the head so that any noise behind the skull is discarded, Such marking did not work perfectly, highlighted areas by color that are clearly not hemorrhage (for example, there is such a gray line in the middle of the skull, it was also sometimes highlighted by this algorithm).
2. Processed all available images through this algorithm + added augmentation, received the initial masks
3. The standard Unet of 10 epochs was trained on the received masks. Got a better result than just OpenCV markup

Conclusions: even on not very well marked data, Unet learns well, provided that there is enough data

Contest website: https://globalai.innopolis.university/

Liderboard on kaggle: https://www.kaggle.com/competitions/innopolis-global-ai-challenge-2023-ai4med

Code on kaggle: https://www.kaggle.com/code/vshakhlin/innopolis-global-ai-challenge-2023-ipynb
