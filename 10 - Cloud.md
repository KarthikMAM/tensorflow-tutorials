
- STEP 1: DOWNLOAD GCLOUD
- STEP 2: EXTRACT IT
- STEP 3: RUN THE `setup.sh` FILE
- STEP 4: `gcloud init`
- STEP 5: `PROJECT_ID=$(gcloud config list project --format "value(core.project)")`
- STEP 6: `BUCKET_NAME=${PROJECT_ID}-mlengine`
- STEP 7: `REGION=us-central1`
- STEP 8: `gsutil mb -l $REGION gs://$BUCKET_NAME`
- STEP 9: `JOB_NAME=job_1`
- STEP 10: `OUTPUT_PATH=gs://$BUCKET_NAME/$JOB_NAME`


#### FINALLY RUN THE ACTUAL JOB

```bash
gcloud ml-engine \ 
  jobs submit training $JOB_NAME \
  --job-dir $OUTPUT_PATH \
  --module-name trainer.task \
  --package-path trainer/ \
  --region $REGION \
  --scale-tier BASIC_GPU
```