Ideas for DeepCover

## Model

* A CNN with this structure seems to do a great job of capturing interactions between the players (taken from [last year's Big Data Bowl winning solution](https://www.kaggle.com/c/nfl-big-data-bowl-2020/discussion/119400)):

![2020BDB](https://www.googleapis.com/download/storage/v1/b/kaggle-user-content/o/inbox%2F85156%2F2b5c9ce8e54f58ba78dcf120ef49c278%2FNN%20structure.png?generation=1574945484839246&alt=media)

Obviously, the actual task needs to be modified: 
* Orientation is likely to be important, and especially orientation to QB
* There are many more offensive players of interest than just one running back
* There are varying numbers of offensive and defensive players on each play
* Last year's BDB only had one frame, so this needs to be extended to something that can handle time data (CNN-LTSM?)

## Things to capture

Any of these should be captured by a good model, but some indicators of zone v man:

* Orientation towards QB or receiver
* Drop depth of intermediate defenders (LBs)
* Situation? (3rd & long more likely two-high?)

## Things to try

* [Augmentation & TTA](https://www.kaggle.com/c/nfl-big-data-bowl-2020/discussion/119400): flip plays along y-axis (see last year's BDB solution)
* Discard very short plays where can't tell what coverage is
* Truncate plays when ball thrown
* Possibly truncate after certain amount of frames have elapsed (zone coverage looks like man after some time has elapsed)
* Treat red zone and / or goal line differently

## Notebooks that classify coverage

* [CoverNet: Evaluating Coverages with a CNN](https://www.kaggle.com/louiszya/covernet-evaluating-coverages-with-a-cnn)
* [Automated play charting with computer vision](https://www.kaggle.com/chrisfenton/uncharted-territory/notebook)
* [A Novel Method For Classifying Pass Defenses at 97% Accuracy](https://www.kaggle.com/powerthinking/how-nfl-pass-defenses-can-learn-from-poker-players) (note: it's possible this is overfit but I can't tell)