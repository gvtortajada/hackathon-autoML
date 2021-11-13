# hackathon-autoML

## Create bucket

```
export PROJECT_ID=$DEVSHELL_PROJECT_ID

export BUCKET=$PROJECT_ID

gsutil mb -p $PROJECT_ID -c standard -l us-central1 gs://${BUCKET}

```

## Copy the images and the metadata file in your bucket

```
gsutil -m cp -r gs://car_damage_lab_images/* gs://${BUCKET}

gsutil cp gs://car_damage_lab_metadata/data.csv .

sed -i -e "s/car_damage_lab_images/${BUCKET}/g" ./data.csv

gsutil cp ./data.csv gs://${BUCKET}

```
