How to Run Jupyter Notebooks on Google Colab Using GCP VM 
# Connecting Google Colab to a GCP VM

## VM Setup


1.   Create the VM on the Google Cloud Console (I kept all default values)
2.   SSH into the VM from a terminal window (You may need to change 8888 to something else):

```
gcloud compute ssh --zone YOUR_ZONE YOUR_INSTANCE_NAME -- -L 8888:localhost:8888
```

3. Install Python
4. Install pip
```
sudo apt install python3-venv python3-pip
```
5. Install Jupyter 
```
pip3 install notebook
```
6. Install and enable Enable the http extension:
```
pip3 install jupyter_http_over_ws
```
7. Restart the session by typing exit and repeating the ssh command in Step 2.
8. Enable the Extension
```
jupyter serverextension enable --py jupyter_http_over_ws
```
8. Make sure to change ```8888``` to whatever you used in step 2.
```
jupyter notebook \
  --NotebookApp.allow_origin='https://colab.research.google.com' \
  --port=8888 \
  --NotebookApp.port_retries=0
```




