# airline-dataset-updater

This repository automatically downloads and updates the Airline Passenger Satisfaction dataset from Kaggle every week.

Overview
- This project uses GitHub Actions to:
- Download the latest version of the Airline Passenger Satisfaction dataset
- Extract train.csv and test.csv into the data/ folder
- Log the update time in _update_log.txt
- Automatically commit changes to the repository every Monday
- Everything runs automatically, with no manual work required.


Update Schedule
- The dataset updates every Monday at 08:00 AM (Taiwan Time).
- Schedule configuration (cron: "0 0 * * 1"):
- 00:00 UTC → 08:00 Taiwan
- GitHub may delay runs by 1–2 hours (normal behavior)


How It Works
  Every Monday:
1- GitHub Actions starts automatically
2- Logs into Kaggle using your stored API key
3- Downloads the dataset ZIP
4- Extracts the CSV files into data/
5- Appends a timestamp to _update_log.txt
6- Commits changes back to the repository

- If the dataset did not change on Kaggle, only _update_log.txt is updated.

