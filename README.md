 # DisasterTweets

> dvc init

> dvc remote add -d storage gdrive://1zQRLy_WQodgS4MBLG57TRsl5LTuKSG5H

> dvc add resources/train.csv
 
 
> dvc run -n split -p split -d resources/train.csv -d src/split.py -o resources/train_data.csv -o resources/test_data.csv python src/split.py

> dvc run -n train -p train -d resources/train_data.csv -d src/train.py -o resources/model.pkl python src/train.py

> dvc run -n eval -p eval -d resources/test_data.csv -d resources/model.pkl -d src/eval.py -M metrics.json python src/eval.py
