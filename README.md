# Laravel Twilio Text App
This is a simple Laravel application that uses Twilio to send and receive text messages and OpenAI's GPT-3 model to generate responses to incoming messages. This app is built using PHP 8.1 and can be run locally or deployed to a production server.

Installation
To run this application locally, you'll need to have the following installed on your machine:

PHP 8.1 or higher
Composer
MySQL or PostgreSQL database
Twilio account with a phone number
OpenAI API key
Follow these steps to install and run the application:

Clone this repository and navigate to the project directory.

``
git clone https://github.com/mastashake08/laravel-twilio-text-app.git
cd laravel-twilio-text-app
``

``composer install``
Rename the .env.example file to .env.

``cp .env.example .env
``

``
APP_URL=http://localhost
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=laravel_twilio_text_app
DB_USERNAME=root
DB_PASSWORD=
``
Set the Twilio account SID, auth token, and phone number in the .env file.

``TWILIO_ACCOUNT_SID=your-account-sid
TWILIO_AUTH_TOKEN=your-auth-token
TWILIO_FROM=your-twilio-phone-number
``
Set the OpenAI API key in the .env file.

``OPENAI_API_KEY=your-api-key
``
Generate a new application key.
``
php artisan key:generate
``
Migrate the database.

``php artisan migrate``
Start the local development server.

``php artisan serve``
Expose your local server to the internet using a tool like ngrok so that Twilio can send messages to your application. Start ngrok using the command ngrok http 8000 and update your Twilio phone number's webhook URL to use the ngrok URL with /incoming-message endpoint.

Send a text message to your Twilio phone number to test the application!

## Docker Installation
Alternatively, you can run this application using Docker. To run this application using Docker, follow these steps:

Clone this repository and navigate to the project directory.

``
git clone https://github.com/mastashake08/laravel-twilio-text-app.git
cd laravel-twilio-text-app
Build the Docker image using the included Dockerfile.
``
``docker build -t your-app-name .``
Run the Docker container.

``docker run -p 8000:9000 -it your-app-name``
Expose your Docker container to the internet using a tool like ngrok so that Twilio can send messages to your application. Start ngrok using the command ngrok http 8000 and update your Twilio phone number's webhook URL to use the ngrok URL with /incoming-message endpoint.

Send a text message to your Twilio phone number to test the application!

License
This application is open-sourced software licensed under the MIT license. Feel free to use, modify, and distribute this application as per the terms of the license. However, please note that this application is provided as-is, without any warranty or support. The authors and contributors to this application shall not be held liable for any damages arising from the use of this application.
