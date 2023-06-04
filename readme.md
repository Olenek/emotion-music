Generates multi-instrument symbolic music (MIDI), based on user-input emotions from valence-arousal plane.

Based on work from paper "Symbolic music generation conditioned on continuous-valued emotions", 
Serkan Sulun, Matthew E. P. Davies, Paula Viana, 2022. 
https://ieeexplore.ieee.org/document/9762257

To create the dataset with Spotify-API:

- Go to the ```src/create_dataset``` folder

- Download the datasets:

Lakh pianoroll 5 full dataset
https://drive.google.com/uc?id=19FJwmNxWUmR3UutCDhZtbKVnEBVHU-2q

MSD summary file
http://labrosa.ee.columbia.edu/millionsong/sites/default/files/AdditionalFiles/msd_summary_file.h5

Echonest mapping dataset
```ftp://ftp.acousticbrainz.org/pub/acousticbrainz/acousticbrainz-labs/download/msdrosetta/millionsongdataset_echonest.tar.bz2```
Alternatively: https://drive.google.com/file/d/1AZctGV7WysvsAaDCPWM1GVBvgaFz2Dys/view?usp=sharing

Lakh-MSD matching scores file
http://hog.ee.columbia.edu/craffel/lmd/match_scores.json

- Extract when necessary, and place all inside folder ```./data_files```

- Get Spotify client ID and client secret:
https://developer.spotify.com/dashboard/applications
Then, fill in the variables "client_id" and "client_secret" in ```src/create_dataset/utils.py```

- Run ```run.py```. 

To preprocess and create the training dataset:

- Go to the ```src/data``` folder and run ```preprocess_pianorolls.py```

To train:

- Go to ```src``` folder and run ```train.py``` with appropriate arguments. e.g:
```python train.py --conditioning```

See ```config.py``` for all options.
