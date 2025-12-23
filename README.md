# EE542-Final_Project_website_code
Note: Ignore the website_code folder. The correct folder is breast_ai_project whoch has backend and frontend folder.
Website code for the AI Breast Cancer detection -deployed on GCP VM -login: http://136.118.169.96:8080
The zip files contains backend and frontend .
However to execute the same on a different machine , other than our GCP, an environment variable WP must be created and pointed to the specific model weights file "best_convnext_small_sigproc_noprior.pt" 
Link here : https://drive.google.com/file/d/1ecNJeZ6E0hBhY12jx_20LUXdDSYVAz--/view?usp=drive_link
This can be done by downlaoding the .pt file and giving the command "export WP="path/to/best_convnext_small_sigproc_noprior.pt"
Then an environment having cuda must be inititiated for example if cuda_anv is name of the conda env - conda activate cuda_env in both backend and frontend folder 
Then in backend the following command in cuda_env environment, "uvicorn app:app --host 0.0.0.0 --port 8005"
And in frontend folder,in cuda_env environment,"python3 -m http.server 8080".
Note: for the backend terminal session WP environment variable must point to "best_convnext_small_sigproc_noprior.pt"
Then the website can be accessed by http://IP:8080 where IP is the public IP of the machine.
