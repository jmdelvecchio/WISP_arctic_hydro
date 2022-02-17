# Exploratory Data Analysis (EDA) for WISP students!
 Part data tutorial, part data exploration with [Evans et al (2020)](https://onlinelibrary.wiley.com/doi/full/10.1002/hyp.13759) hydro data for Dartmouth interns
 
 The Women In Science Project gets first-year women at Dartmouth College into research labs, and our lab is working with geospatial data in the Arctic. An essential part of this work will be taking existing data and extracting new topographic or ecological data that might explain historical trends others observe. For that we need to practice acquiring, cleaning and plotting "wide" datasets both as tabular and spatial data. 
 
 The following assumes you've had some success setting up a conda environment in Dartmouth's shared-memory computers and opened Jupyter notebook before:
 https://services.dartmouth.edu/TDClient/1806/Portal/KB/ArticleDet?ID=72886
 https://services.dartmouth.edu/TDClient/1806/Portal/KB/ArticleDet?ID=72888
 https://services.dartmouth.edu/TDClient/1806/Portal/KB/ArticleDet?ID=124517
 ## Set up
 1. Use command prompt to `ssh` into Polaris or Andes:
 `ssh xxxxxxx@[polaris/andes]@dartmouth.edu`
 2. Create a new environment `git-env` to install git (I have had problems installing git on base environments)
 <br>`conda create --name git-env`
 
 3. Activate your new environment with `conda activate git-env` and then clone the repository:
 <br>`git clone https://github.com/jmdelvecchio/WISP_arctic_hydro.git`
 
 4. Navigate to the `WISP-arctic-hydro` directory (folder) with `cd WISP-arctic-hydro` (tip: start typing "WI" and then hit "tab", it'll autocomplete!)
 
 5. Create another new environment for your EDA with the yml file:
 <br>`conda env create -f environment.yml`
 
 6. Activate that new environment with `conda activate wisp_eda`
 
 7. Launch Jupyter notebook (if you're doing on Andes or Polaris, use no browser mode)
 <br>`jupyter notebook --no-browser`
 and don't forget to ssh tunnel for the notebook.
 
 8. Open another instance of your prompt and write
 <br>`ssh -NfL xxxx:localhost:xxxx [your_user_ID]@[andes/polaris].dartmouth.edu`
 where `xxxx` is the four-digit localhost:xxxx port you see when you launch Jupyter Notebook 
 
 9.  'Splore some data (after importing your libraries!!)! Two hints:
 
 You will need to call your .csv tables from the `data_tables` directory, but I would *recommend* having your Jupyter Notebook file in your main WISP folder. What I do is designate a `data_dir` variable with the path of the directory in which I place my data, like so:
 `data_dir = './data_tables/'`
 The `.` tells you to use the current working directory (WISP) and then look for a directory called `data_tables`. I then use `os.path.join()` (info [here](https://docs.python.org/3/library/os.path.html)) when loading to pandas:
 `df = pd.read_csv(os.path.join(data_dir,'evans_hydro_supplement.csv')`
 
 BUT! You will see I have been very cruel and copy and pasted *directly* from the supplement, so pandas will not be happy.
 I'll help you out here: read in the csv with a special-characters encoding, and then write a new csv with utf-8 encoding (some realistic data cleaning for you!)<br>
 `df = pd.read_csv(os.path.join(data_dir,'evans_hydro_supplement.csv'), encoding='windows-1254')
 df.to_csv(os.path.join(data_dir,'evans_hydro_supplement_new.csv'), encoding='utf-8', index=False)`
 
 Now try `df = pd.read_csv(os.path.join(data_dir,'evans_hydro_supplement_new.csv'))` and see how it goes.




My idea here with you cloning this repository with git (rather than just me emailing you data) is that as we progess (read: as I figure out how to do things) I will add GIS files and scripts so we can do geospatial data analysis once we get there, and I can push those updates and you can pull them like real programmers...or something. 
