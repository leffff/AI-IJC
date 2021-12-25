# AI-IJC
Our top 1 solution to [AI IJC](https://aiijc.com/en/about) Customer Service team round task </br></br>
![alt text](leaderboard.png)</br></br>

Contest description:</br>
Our task was to predict aggressive driving among taxi drivers using following data types: taxi route, customer comment about the ride, other table data about the order.</br>
There were only two labeld in the dataset: ```0``` which meant unaggressive driving and ```1```, which symbolized aggressive driving. The dataset was imbalanced with about 96% of ```0``` labels and only 4% of ```1```. Also the dataset itself didn't have commnets for every order, which made it hard to train big supervised models.</br>
However we had a whole dataset of unlabeled comments. Which we were to use.

Solution description:</br>
1. The best score was achieved with a text model [sismetanin/xlm_roberta_base-ru-sentiment-rusentiment](sismetanin/xlm_roberta_base-ru-sentiment-rusentiment)
2. We did EDA and found senseless comments like "Да", "Нет", "." etc.
3. Implement UDA in order to use unlabeled samples. [Original PyTorch UDA implementation](https://github.com/SanghunYun/UDA_pytorch)
4. We used back translation to English as an augmentation of unlabeld data.
5. We chose [Cross Entropy](https://pytorch.org/docs/stable/generated/torch.nn.CrossEntropyLoss.html?highlight=cross%20entropy#torch.nn.CrossEntropyLoss) as supervised loss and [KL Divergece](https://pytorch.org/docs/stable/generated/torch.nn.KLDivLoss.html) as unsupervised loss


