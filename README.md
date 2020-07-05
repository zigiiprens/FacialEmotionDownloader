## Download kaggle 

Official API for https://www.kaggle.com, accessible using a command line tool implemented in Python 3.

Beta release - Kaggle reserves the right to modify the API functionality currently offered.

IMPORTANT: Competitions submissions using an API version prior to 1.5.0 may not work. If you are encountering difficulties with submitting to competitions, please check your version with "kaggle --version". If it is below 1.5.0, please update with "pip install kaggle --upgrade".

## API credentials

To use the Kaggle API, sign up for a Kaggle account at https://www.kaggle.com. Then go to the 'Account' tab of your user profile (https://www.kaggle.com/<username>/account) and select 'Create API Token'. This will trigger the download of kaggle.json, a file containing your API credentials. Place this file in the location ~/.kaggle/kaggle.json

For your security, ensure that other users of your computer do not have read access to your credentials. On Unix-based systems you can do this with the following command:

    chmod 600 ~/.kaggle/kaggle.json


## Downloader command

    kaggle competitions download -c challenges-in-representation-learning-facial-expression-recognition-challenge

When I have tried this command, I get this error:

    ▶ "pipenv run"/"pip" kaggle competitions download -c challenges-in-representation-learning-facial-expression-recognition-challenge
    Warning: Your Kaggle API key is readable by other users on this system! To fix this, you can run 'chmod 600 /Users/kentkart/.kaggle/kaggle.json'
    403 - Forbidden
    (FacialEmotionDownloader)

So I start searching another way to download dataset, and I faced in that issue https://github.com/Kaggle/kaggle-api/issues/160 that:

    you might need to agree to the competitions terms before you can download via api. That's what happened to me.

Another way was to find an open dataset that can be easily download:

    "pipenv run"/"pip" kaggle datasets download -d debanga/facial-expression-recognition-challenge

And finally, the dataset was loading.... But you need to extract it.