# WISP_arctic_hydro
 Part data tutorial, part data exploration with [Evans et al (2020)](https://onlinelibrary.wiley.com/doi/full/10.1002/hyp.13759) hydro data for Dartmouth interns
 
 ## Set up
 1. Fork repository
 2. Navigate to the repository in command prompt/anaconda prompt
 3. Create environment with the yml file:
 `conda env create -f environment.yml`
 You should see an environment `wisp-eda` with a call to `conda env list`
 4. Launch Jupyter notebook (if you're doing on Andes or Polaris, use no browser mode)
 `jupyter notebook --no-browser`
 and don't forget to ssh tunnel for the notebook. Open another instance of your prompt and write
 `ssh -NfL xxxx:localhost:xxxx [your_user_ID]@[andes/polaris].dartmouth.edu`
 where `xxxx` is the four-digit localhost:xxxx port you see when you launch Jupyter Notebook 
 5. 'Splore some data! 
 
 My idea here with you forking this repository is that as we progess (read: as I figure out how to do things) I will add GIS files and scripts so we can do geospatial data analysis once we get there, and I can push those updates and you can pull them like real programmers...or something. 
