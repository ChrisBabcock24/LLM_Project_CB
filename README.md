# LLM Project

## Project Task
This project aimed to summarize news articles from the *multi_news* dataset in an accurate and efficient manner.

## Dataset
For this project, I chose the *multi_news* dataset, which contains news articles along with human-written summaries. According to the dataset card, it includes two features: 
- **Document**: The full text of the articles.
- **Summary**: The corresponding summary for each article.

## Pre-trained Model
Initially, I explored the *facebook/bart-large-cnn* model, but I found that it required substantial computational resources. To optimize resource usage, I switched to the *facebook/bart-base* model, which demands fewer resources while still performing well.

## Performance Metrics
To evaluate the performance of my model, I used ROUGE metrics, which are particularly effective for summarization tasks.

### Results
The model achieved the following ROUGE scores:
- **ROUGE-1 F1 Score**: 0.4048
- **ROUGE-2 F1 Score**: 0.1271
- **ROUGE-L F1 Score**: 0.3715

These results indicate that the model was effective at capturing key ideas (ROUGE-1), but there is room for improvement with bigrams (ROUGE-2). The ROUGE-L score suggests a good alignment with the reference summaries.

## Hyperparameters
The learning rate was crucial for improving my model's performance. I implemented a learning rate scheduler to gradually reduce the rate as the model converged. Given the limited resources and the large size of the dataset, batch sizes were particularly important for functionality. I also utilized gradient accumulation to simulate larger batches without sacrificing memory. Additionally, I trained using chunks of the dataset to manage memory usage and avoid exceeding available memory limits.

## Deployment
After making some adjustments to the hyperparameters and training the model I evaluated and deployed to Hugging Face.
Link Here - [text](https://huggingface.co/Chribabc/LLM_Project_Lighthouse)