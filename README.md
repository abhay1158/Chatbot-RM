# Chatbot

It uses Celery for task scheduling and can be
deployed on AWS using Elastic Beanstalk, EC2, and ElastiCache for Redis.


## Installation

- Install the required Python packages:
    ```
    pip install -r requirements.txt
    ```
- Set up the environment variables in the `.env` file:
    ```
    GOOGLE_API_KEY=your_google_api_key
    GOOGLE_CLIENT_ID=your_google_client_id
    GOOGLE_CLIENT_SECRET=your_google_client_secret
    OPENAI_API_KEY=your_openai_api_key
    REDIS_URL=redis://your_redis_server:port/db
    ```

## Usage

- Run the chatbot locally:
    ```
    python google_reviews_chatbot.py
    ```
- Run Celery worker for task scheduling:
    ```
    celery -A celery_worker worker --loglevel=info
    ```
- Run Celery beat for periodic task execution:
  ```
  celery -A celery_worker beat --loglevel=info
  ```
