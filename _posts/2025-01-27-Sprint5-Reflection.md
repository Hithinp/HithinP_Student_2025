
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
            <h2>Detecting Stress or Depression</h2>
            <p>To identify users who may be feeling distressed, I implemented a keyword-based detection mechanism:</p>
            <code class="snippet">
<img src="{{site.baseurl}}/images/CSP_MCQ/Screenshot 2025-01-27 at 10.15.06 PM.jpeg" alt="Screenshot 1" style="width: 150%; margin-bottom: 10px; border: 2px solid #1b5e20; border-radius: 5px;">
            <p>When a user's message contains specific keywords related to self-harm or distress, the system flags their mood as "distressed" and sends this data to the backend for further action.</p>
            <h2>Updating the Backend</h2>
            <p>In the backend, the user's mood is stored in a database next to their username. Here's the implementation:</p>
            <code class="snippet">
<img src="{{site.baseurl}}/images/CSP_MCQ/Screenshot 2025-01-27 at 10.15.51 PM.jpeg" alt="Screenshot 1" style="width: 150%; margin-bottom: 10px; border: 2px solid #1b5e20; border-radius: 5px;">

    <footer>
        <p>Striver Blog &copy; 2025</p>
    </footer>

