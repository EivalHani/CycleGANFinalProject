# CycleGANFinalProject
 General Description
 
Our system embeds a patient's medical diagnosis image within a container image, preserving the sensitive information's full medical confidentiality. The system is also capable of restoring the original medical image.
Our system offers a secure and convenient method of transferring sensitive information.

  Software Environment
  
●	Colab: Used Colab to execute shell commands.

  Running Instruction
  
Follow these additional steps:

1. Upload the code directory  folder to your drive.
2. Open the CycleGanProjFinal.ipynb file on Google Colab from your drive.
3. Press Runtime -> Run all
4. See the results: Go to the results directory -> MRItoZebra -> test_345 (or other number if you chose other epoch)

or:

1. connect tou you google Drive:
from google.colab import drive
drive.mount('/content/drive')

2. nevigate:
   cd drive
   cd MyDrive
   cd CycleGANTrained

3. install requirements file:
   !pip install -r requirements.txt

4. install:
   !pip install dominate
   !pip install visdom

5. test the trained model. we trained it until epoch 345 so you can choose to see the test results according to any epoch you choose until 345. 345 is the most trained. 
   !python test.py --dataroot /content/drive/MyDrive/CycleGANTrained/dataset --name MRItoZebra --model cycle_gan --epoch 345

6. See the results:
   Go to the results directory -> MRItoZebra -> test_345 (or other number if you chose other epoch)

More:

If you want to keep training, add a cell and run: 

With constant learning rate (change the epoch from the starting epoch you choose):
!python train.py --dataroot /content/drive/MyDrive/CycleGANTrained/dataset --name MRItoZebra --model cycle_gan --continue_train --epoch_count 201 --n_epochs 400 --n_epochs_decay 10000 --lr 0.0002


In this command, We set n_epochs_decay to 10000. This means that the learning rate will start decaying only after 10000 epochs, which effectively makes the learning rate constant at 0.0002 for the training duration of less than 1000 epochs. If you want more than 10000 just change the n_epochs_decay number.



if you want a decay learning rate(change the epoch from the starting epoch you choose):

!python train.py --dataroot /content/drive/MyDrive/CycleGANTrained/dataset --name MRItoZebra --model cycle_gan --continue_train --epoch_count 296 --n_epochs 295 --n_epochs_decay 200 --lr 0.0002 --display_id 0


epoch_count is on which epoch we are now, n_epochs is the number of epochs with a constant learning rate and n_epochs_decay is the count of epochs from now until the learning rate will get to 0.


Good Luck!



   


