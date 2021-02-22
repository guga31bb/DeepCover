Ideas for DeepCover

## Model

* A CNN with this structure seems to do a great job of capturing interactions between the players (taken from [last year's Big Data Bowl winning solution](https://www.kaggle.com/c/nfl-big-data-bowl-2020/discussion/119400)):

![2020BDB](https://www.googleapis.com/download/storage/v1/b/kaggle-user-content/o/inbox%2F85156%2F2b5c9ce8e54f58ba78dcf120ef49c278%2FNN%20structure.png?generation=1574945484839246&alt=media)

Obviously, the actual inputs need to be different. For one, orientation is likely to be important, and especially orientation to QB. For another, there are many more offensive players of interest than just one running back. In addition, there are varying numbers of offensive and defensive players on each play. Finally, last year's BDB only had one frame, so this needs to be extended to something that can handle time data (CNN-LTSM?).

## Things to try

* [Augmentation & TTA](https://www.kaggle.com/c/nfl-big-data-bowl-2020/discussion/119400): flip plays along y-axis (see last year's BDB solution)