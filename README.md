# Sentiment-analysis-from-audio-file
Uses AWS transcribe and comprehend sentiment analysis to run sentiment analysis from an audio file.

Start by creating 3 S3 buckets
  1. Audio file bucket
  2. Transcription bucket
  3. Finished analysis bucket
  
  Buckets 1 and 2 will both have event triggers for lambda function.
    Bucket one for the "Lambda-for-transcribe" function which will then deposit a transcription json file into bucket 2
    Bucket two for the "Lambda-for-sentiment-comprehend" function which will then deposit a analyzed sentiment json file
      into bucket 3.
      
   Lambda-for-sentiment-comprehend extracts the transcription data from the transcribed json file before running the sentiment analysis on the data. It then provides information on the language, sentiment, and sentiment score of the audio's text.
