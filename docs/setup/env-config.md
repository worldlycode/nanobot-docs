# Setting up the `.env` file


Create a `.env` file in the root directory with the following variables:
```
OPENAI_API_KEY=your_openai_api_key
LOCAL_DB_NAME=nanobot
LOCAL_DB_USER=postgres
LOCAL_DB_PASSWORD=your_password
LOCAL_DB_HOST=localhost
LOCAL_DB_PORT=5432
LOGFIRE_TOKEN=your_logfire_token
NEON_URL=your_neon_db_url
USE_NEON=False (defaults to using local db)
```

* If you do not have a Logfire token please see the [Logfire-Setup Page](logfire-setup.md)

* If you do not have a Neon URL please see the [Neon-Setup Page](neon-setup.md)


