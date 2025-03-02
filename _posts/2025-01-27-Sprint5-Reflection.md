
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Striver Blog</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f9;
        }

        header {
            background-color: #d4edda; /* Light green background */
            color: #333;
            padding: 1rem;
            text-align: center;
        }

        main {
            max-width: 800px;
            margin: 2rem auto;
            padding: 1rem;
            background: white;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }

        h1, h2 {
            color: #333;
        }

        code {
            display: block;
            background: #e8e8e8;
            padding: 10px;
            border-radius: 5px;
            overflow-x: auto;
            margin: 1rem 0;
            white-space: pre-wrap;
            font-family: 'Courier New', Courier, monospace;
        }

        .snippet {
            font-family: 'Courier New', Courier, monospace;
        }

        footer {
            text-align: center;
            margin-top: 2rem;
            padding: 1rem;
            background: #4caf50;
            color: white;
        }

        .highlight-text {
            color: #42a5f5; /* Light blue color */
            font-weight: bold;
            font-size: 1.2rem;
            text-align: center;
            display: block;
            margin-top: 1rem;
        }
    </style>
</head>
<body>
    <header>
        <h1>Welcome to Striver</h1>
        <p class="highlight-text">Empowering growth, celebrating achievements, connecting journeys, inspiring brighter futures</p>
    </header>
    <main>
        <section>
            <h2>What is Striver?</h2>
            <p>Striver is a website where you can share your achievements and challenges. It provides a platform to interact with others, celebrate victories, and support one another through difficult times.</p>
        </section>
        <section>
            <h2>My Task</h2>
            <p>My task was to integrate Gemini AI into Striver to create an interactive chatbot. This chatbot acts like a therapist and a supportive friend, providing users with a safe and empathetic space to express themselves.</p>
        </section>
        <section>
            <h2>Code Explanation</h2>
            <p>The following snippet shows how I communicated with the Gemini AI to create conversational responses:</p>
            <code class="snippet">
<img src="{{site.baseurl}}/images/CSP_MCQ/Screenshot 2025-01-27 at 10.03.15 PM.jpeg" alt="Screenshot 1" style="width: 150%; margin-bottom: 10px; border: 2px solid #1b5e20; border-radius: 5px;">
           </code>
           <p>This function sends a user's message to the Gemini API and receives a conversational response. The chatbot is designed to be warm, relatable, and conversational, offering a human-like interaction.</p>

<header>
        <h1>Input/Output requests. Demo ways to Input to your full stack feature.</h1>
<img src="{{site.baseurl}}/images/CSP_MCQ/Screenshot 2025-01-30 at 10.21.21 PM.jpeg" alt="Screenshot 1" style="width: 150%; margin-bottom: 10px; border: 2px solid #1b5e20; border-radius: 5px;">
<p>A user composes and sends a message to Striver. The message could be a query about programming, career advice, or personal development, depending on the purpose of the message . Striver analyzes whether the user has used words that may indicate depression.
</p>

<hr>
<img src="{{site.baseurl}}/images/CSP_MCQ/Screenshot 2025-01-27 at 10.15.06 PM.jpeg" alt="Screenshot 1" style="width: 150%; margin-bottom: 10px; border: 2px solid #1b5e20; border-radius: 5px;">
<p>When a user's message contains specific keywords related to self-harm or distress, the system flags their mood as "distressed" and sends this data to the backend for further action.
</p>


<hr>
<img src="{{site.baseurl}}/images/CSP_MCQ/Screenshot 2025-01-30 at 10.52.27 PM.jpeg" alt="Screenshot 1" style="width: 150%; margin-bottom: 10px; border: 2px solid #1b5e20; border-radius: 5px;">
<p>A Blueprint (mood_api) is created to modularize the API. A flask_restful.Api object (api) is attached to the Blueprint. This allows adding RESTful resources.
</p>

<hr>
<img src="{{site.baseurl}}/images/CSP_MCQ/Screenshot 2025-01-30 at 10.58.38 PM.jpeg" alt="Screenshot 1" style="width: 150%; margin-bottom: 10px; border: 2px solid #1b5e20; border-radius: 5px;">
<p>This method handles both creating and updating a mood entry for an authenticated user.
@token_required() ensures only authenticated users can access this route.
request.get_json() extracts the mood from the request body.
Validation: Checks if mood is a non-empty string.
</p>

<hr>
<img src="{{site.baseurl}}/images/CSP_MCQ/Screenshot 2025-01-30 at 11.03.17 PM.jpeg" alt="Screenshot 1" style="width: 150%; margin-bottom: 10px; border: 2px solid #1b5e20; border-radius: 5px;">
<p>This code checks if the user already has a mood entry in the database. If an existinge entry is found it willl update the mood field depending on what is detected from the current message of the user
</p>

<hr>
<img src="{{site.baseurl}}/images/CSP_MCQ/Screenshot 2025-01-30 at 11.08.48 PM.jpeg" alt="Screenshot 1" style="width: 150%; margin-bottom: 10px; border: 2px solid #1b5e20; border-radius: 5px;">
<p>First ensures the user's mood entry in teh datbase and then if it exists the current mood gets erased until the user types a new message and the frontend will once again check if the suer is depressed or neutral.
</p>

<hr>


<header>


<h1>List requests.  Use of list, dictionaries and database.  Code descriptions of area where you work with list (rows) and dictionaries (columns) of the database.</h1>
<p>This Flask-RESTful API allows authenticated users to Create, Read, Update, and Delete (CRUD) mood entries using a Blueprint and Flask-RESTful. The /api/mood endpoint handles adding or updating a user's mood, where the API first checks if the user already has an entry—if so, it updates it; otherwise, it creates a new one. The /api/mood/restore endpoint allows users to erase their mood entry by setting it to None. Both endpoints require authentication via a @token_required() decorator. The API follows proper validation, error handling, and response formatting to ensure reliability. By using a modular structure with Blueprints, it efficiently manages user moods while maintaining security and scalability.
</p>
<hr>
<img src="{{site.baseurl}}/images/CSP_MCQ/Screenshot 2025-01-30 at 11.55.46 PM.jpeg" alt="Screenshot 1" style="width: 150%; margin-bottom: 10px; border: 2px solid #1b5e20; border-radius: 5px;">
<p>The extract_data() function plays a critical role in aggregating and organizing data from various database models into a dictionary structure. It operates within the context of the Flask application (with app.app_context()), ensuring database queries are appropriately bound to the current app context. The function queries tables such as User, Section, Group, Channel, Post, and Mood, among others, using the query.all() method. This retrieves a list of all rows from each table. The read() method is then called on each row object to convert it into a dictionary, which is essential for serializing the data into JSON format for APIs. However, there is a notable issue in the snippet where data['mood'] mistakenly queries User.query.all() instead of Mood.query.all(), which appears to be a copy-paste error. Correcting this would ensure that mood-specific data is extracted and formatted correctly.
</p>
<hr>
<img src="{{site.baseurl}}/images/CSP_MCQ/Screenshot 2025-01-30 at 11.57.20 PM.jpeg" alt="Screenshot 1" style="width: 150%; margin-bottom: 10px; border: 2px solid #1b5e20; border-radius: 5px;">
<p>The login route is a fundamental part of user authentication in the system, handling both GET and POST requests. When a user submits their credentials through a POST request, the application retrieves the corresponding user record from the database using User.query.filter_by(_uid=request.form['username']).first(). This query returns the first match based on the provided username. If the user exists and their password matches the stored hash (verified by user.is_password(request.form['password'])), the login_user(user) function logs them into the application. The next_page parameter is checked to ensure that it directs the user to a safe URL; otherwise, the request is aborted with a 400 error. This snippet demonstrates a common pattern of querying the database, handling authentication logic, and providing secure redirection. If mood-related analytics were integrated, Gemini AI could potentially analyze user behavior during login attempts to offer insights or detect signs of frustration.
</p>

<hr>
<img src="{{site.baseurl}}/images/CSP_MCQ/Screenshot 2025-01-30 at 11.58.15 PM.jpeg" alt="Screenshot 1" style="width: 150%; margin-bottom: 10px; border: 2px solid #1b5e20; border-radius: 5px;">
<p>The Mood class is a model that maps to the Mood database table, representing mood-related data. It includes three columns: id, mood_type, and description. The id column serves as the primary key, uniquely identifying each record. The mood_type column is a string field for storing different mood categories (e.g., happy, anxious), while description provides additional context or notes about the mood entry. The read() method is defined to return a dictionary representation of the object, which is essential for converting the model's data into a JSON-friendly format for API responses. This model structure makes it straightforward to manage and retrieve mood data, forming a foundation for mood-related API functionalities and potential AI-driven mood analysis using Gemini AI.
</p>

<hr>
<h1>frontend-backend integration</h1>
<img src="{{site.baseurl}}/images/CSP_MCQ/Screenshot 2025-01-30 at 11.58.15 PM.jpeg" alt="Screenshot 1" style="width: 150%; margin-bottom: 10px; border: 2px solid #1b5e20; border-radius: 5px;">
<p>User types a message
</p>

<hr>
<img src="{{site.baseurl}}/images/CSP_MCQ/Screenshot 2025-01-31 at 8.51.05 AM.jpeg" alt="Screenshot 1" style="width: 150%; margin-bottom: 10px; border: 2px solid #1b5e20; border-radius: 5px;">
<p>Backend displays current mood
</p>

<hr>
<img src="{{site.baseurl}}/images/CSP_MCQ/Screenshot 2025-01-31 at 12.06.37 AM.jpeg" alt="Screenshot 1" style="width: 150%; margin-bottom: 10px; border: 2px solid #1b5e20; border-radius: 5px;">
<p>user types a key word that indicates them being dipressed
</p>

<hr>
<img src="{{site.baseurl}}/images/CSP_MCQ/Screenshot 2025-01-31 at 8.46.47 AM.jpeg" alt="Screenshot 1" style="width: 150%; margin-bottom: 10px; border: 2px solid #1b5e20; border-radius: 5px;">
<p>Backend updates current mood 
</p>

<hr>
<img src="{{site.baseurl}}/images/CSP_MCQ/Screenshot 2025-01-31 at 12.12.59 AM.jpeg" alt="Screenshot 1" style="width: 150%; margin-bottom: 10px; border: 2px solid #1b5e20; border-radius: 5px;">
<p>user clicks restore mood
</p>

<hr>
<img src="{{site.baseurl}}/images/CSP_MCQ/Screenshot 2025-02-03 at 2.50.55 PM.jpeg" alt="Screenshot 1" style="width: 150%; margin-bottom: 10px; border: 2px solid #1b5e20; border-radius: 5px;">
<p>Backend updates current mood 
</p>


<hr>
<img src="{{site.baseurl}}/images/CSP_MCQ/Screenshot 2025-01-31 at 2.47.26 PM.jpeg" alt="Screenshot 1" style="width: 150%; margin-bottom: 10px; border: 2px solid #1b5e20; border-radius: 5px;">
<p>This code defines two methods, read and clear, which are likely part of a database model using an ORM like SQLAlchemy. The read method returns a dictionary containing the object's id, mood, and user_id, allowing for easy serialization of the object, which is useful for API responses or data processing. The clear method is responsible for deleting the instance from the database. It first attempts to remove the object using db.session.delete(self), followed by db.session.commit() to finalize the deletion. If an error occurs during this process, the exception is caught, and db.session.rollback() is executed to undo any partial changes before re-raising the exception. This ensures data integrity and prevents database corruption in case of unexpected errors. 
</p>

<hr>
<img src="{{site.baseurl}}/images/CSP_MCQ/Screenshot 2025-01-31 at 2.58.56 PM.jpeg" alt="Screenshot 1" style="width: 150%; margin-bottom: 10px; border: 2px solid #1b5e20; border-radius: 5px;">
<p>This updated get method allows users to retrieve mood entries based on a specified user_id. It first extracts the user_id from the request’s query parameters and checks whether it is provided. If no user_id is supplied, it returns an error message with a 400 status code. The method then queries the Mood table to fetch all mood entries associated with that user_id. If no moods are found, it returns a 404 error indicating that no records exist for the given user. Otherwise, it formats the retrieved mood entries as a JSON response by calling their read method. This ensures that users can easily fetch and view mood data related to specific individuals.
</p>
