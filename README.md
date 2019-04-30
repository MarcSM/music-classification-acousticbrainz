# Music Classification with AcousticBrainz

This is a exploration task of genres and subgenres by music descriptors. After taking care of some aspects about the data, one of the four datasets is selected to perform this analysis.

## Project notes

### 1. Taking the four genre datasets and computing the intersection of all of them, based on the recording ID. Music features are used for this intersection.¶

First I have defined some structures and dictionaries to keep all the data well indexed and accessible. Then there are two functions: “load_datasets” which loads all the datasets defined in the “datasets” dictionary, In the first run it only loads the id’s because first we only need to compute the intersection so there is no need to load all the data.

### 2. Selecting one dataset to use out of the four (AllMusic, Discogs, Last.fm, or Tagtraum, we will be using Tagtraum in this case). Preparing the corresponding subset of the genre and subgenre annotations and the features.

Once we have the intersected id’s, I have chosen “Tagtraum” and now we load all the dataset properties, no only the id’s, calling the funcion “load_dataset_recordings”. Now all the recordings are stored into the dictionary so we can easily access them through the dictionary with “datasets[“tagtraum”] [“recordings”]”. In that step, we only keep the id’s that have been present in the intersection in the previous step.

Afterwards, we load the dataset with selected features and do an embedding to have all the information in the “datasets[“tagtraum”] [“recordings”]” dictionary.

### 3. Selecting a set of 20 subgenres to work with.

In this section first I thought about take the most important subgenres, but then I realized that the majority of them will be related with rock so I chose some subgenres of my own interest manually in order to have some diversity in the analysis and the ending results. In that step, we only keep the recordings that belongs to any of the selected subgenres. I've tried to select a few subgenres per genre to cover different types of music in the analysis.

### 4. Comparing the selected subgenres in terms of the distribution of their music features.

Here I have just tried to display a comparative table with the average of all the features for all the genres. I also have a comparative graph that show better this subgenre-feature relationship.



### 5. Making comparative plots of the distributions of the feature values for each subgenre.

In this secton we have box plots, not computed with the average like in the previous graph, but with all the feature values of all the recordings for every sub genre. I won’t show here all the plots, as they are many and this will get unnecessarily long, but I will post one about the bpm across all the subgenres that I’ve particularly liked.



### 6. Making comparative plots analyzing high-level (classifier based) music features.

Here the same, the code and the “Output Plots” folder are plenty of plots. There are plots showing the correlations of music mood estimations (happy, sad, relaxed, aggressive, party) to subgenres and others showing the correlations of vocal/instrumental, male/female voice, danceability classifier estimations to subgenres. The high level features sometimes nail the emotions, but sometimes not, here is one that I think it’s quite decent about danceability, here the numbers are very tiny, please see them all in the folders. 



## Setup and run

Please follow the instructions below to set up the required software in your computer and be able to run the notebooks.

### 1) Install Docker

It is recommended to read the documentation about [Docker](https://docs.docker.com/)
and [docker-compose](https://docs.docker.com/compose/).

#### Windows
https://docs.docker.com/docker-for-windows/install/

#### Mac
https://docs.docker.com/docker-for-mac/install/

#### Ubuntu
https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/#install-docker-ce

### 2) Install docker-compose

Follow [instructions](https://docs.docker.com/compose/install/).
Depending on your operartive system, this step won't be necessary because `docker-compose` will already have been installed in step 1).

### 3) Run the notebooks

Run the following command to startup the notebooks server:

    docker-compose up

Then access `http://localhost:8888` on your browser and when asked for a password use **mir**.