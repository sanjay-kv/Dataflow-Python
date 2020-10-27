# Dataflow-Python

set up your Python development environment, get the Cloud Dataflow SDK for Python, and run an example pipeline using the Cloud Console.

Step 1: Open Cloud Shell

gcloud config set account `ACCOUNT`

gcloud config list project

Check the Permision in IAM & Admin  -> Create Bucket -> Installation 
-------
# Follow this commands in Cloud shell

python3 --version

pip3 --version

sudo pip3 install -U pip

sudo pip3 install --upgrade virtualenv

virtualenv -p python3.7 env

source env/bin/activate

pip install apache-beam[gcp]

python -m apache_beam.examples.wordcount --output OUTPUT_FILE

ls

cat <file name>        #In the above command output you will get the file name Copy paste the same.
  
#  Step 2----------Run Sample Pipeline now
  
  BUCKET=gs://<bucket name provided earlier>
  
  python -m apache_beam.examples.wordcount --project $DEVSHELL_PROJECT_ID \
  --runner DataflowRunner \
  --staging_location $BUCKET/staging \
  --temp_location $BUCKET/temp \
  --output $BUCKET/results/output \
  --region us-central1
  
  
  
