---
layout: base
title: MCQ_CSP
permalink: /MCQ_CSP
---

<!-- Header Section -->
<div style="background-color: #e3f2fd; padding: 20px; border-radius: 10px; text-align: center;">
    <h1 style="font-size: 40px; color: #0d47a1; font-family: 'Times New Roman', sans-serif;">MCQ CSP Progress</h1>
    <p style="font-size: 90%; color: #0d47a1; font-weight: bold; font-size: 20px;">Current Score: <span style="font-size: 45px; color: #1976d2;">59/66 and took 2.5 hours</span></p>
</div>

<!-- Analysis Section -->
<div style="margin-top: 20px; background-color: #fbe9e7; padding: 15px; border-radius: 10px;">
    <h2 style="color: #d84315; font-family: 'Times New Roman', sans-serif;">Analysis of Mistakes</h2>
    <p style="font-size: 18px; color: #5d4037;">
        Overall, the mistakes highlight a need to focus on understanding data scope, applying logic to programming rules, and interpreting algorithm performance. 
        <br><br>
        <strong>Key Issues:</strong>
        <ul style="color: #6d4c41; font-size: 16px;">
            <li>In the first question, the error came from underestimating the inferences possible from the given data. Practice analyzing datasets for all potential calculations.</li>
            <li>The second question highlighted a misunderstanding of replacement rules. Improve programming logic, particularly with conditions and calculations.</li>
            <li>The third question revealed a gap in understanding time complexity; polynomial growth was incorrectly judged as unreasonable.</li>
        </ul>
    </p>
</div>

<!-- Images Section -->
<div style="margin-top: 20px;">
    <h2 style="color: #1b5e20; font-family: 'Times New Roman', sans-serif; text-align: center;">Key Screenshots</h2>
    <div style="text-align: center;">
        <img src="{{site.baseurl}}/images/CSP_MCQ/Screenshot 2024-11-19 at 3.06.41 PM.jpeg" alt="Screenshot 1" style="width: 80%; margin-bottom: 10px; border: 2px solid #1b5e20; border-radius: 5px;">
        <img src="{{site.baseurl}}/images/CSP_MCQ/Screenshot 2024-11-19 at 12.12.21 PM.jpeg" alt="Screenshot 2" style="width: 80%; margin-bottom: 10px; border: 2px solid #1b5e20; border-radius: 5px;">
        <img src="{{site.baseurl}}/images/CSP_MCQ/Screenshot 2024-11-19 at 12.12.46 PM.jpeg" alt="Screenshot 3" style="width: 80%; margin-bottom: 10px; border: 2px solid #1b5e20; border-radius: 5px;">
        <img src="{{site.baseurl}}/images/CSP_MCQ/Screenshot 2024-11-19 at 12.13.16 PM.jpeg" alt="Screenshot 4" style="width: 80%; margin-bottom: 10px; border: 2px solid #1b5e20; border-radius: 5px;">
        <img src="{{site.baseurl}}/images/CSP_MCQ/Screenshot 2024-11-19 at 12.13.40 PM.jpeg" alt="Screenshot 5" style="width: 80%; margin-bottom: 10px; border: 2px solid #1b5e20; border-radius: 5px;">
        <img src="{{site.baseurl}}/images/CSP_MCQ/Screenshot 2024-11-19 at 12.14.01 PM.jpeg" alt="Screenshot 6" style="width: 80%; margin-bottom: 10px; border: 2px solid #1b5e20; border-radius: 5px;">
        <img src="{{site.baseurl}}/images/CSP_MCQ/Screenshot 2024-11-19 at 12.14.33 PM.jpeg" alt="Screenshot 7" style="width: 80%; margin-bottom: 10px; border: 2px solid #1b5e20; border-radius: 5px;">
    </div>
</div>





<div style="background-color: #f7d1d1; padding: 20px; border-radius: 10px; border: 2px solid #f2a3a3;">
  <h3 style="font-size: 18px; color: #9e3a3a; font-family: 'Times New Roman', serif; font-weight: bold;">Why I Got These Questions Wrong</h3>
  <p style="font-size: 16px; color: #9e3a3a; font-family: 'Times New Roman', serif;">
    I made these mistakes mainly because I didn't take enough time to reread the questions and focus on the key details. In some cases, I overlooked specific instructions or misunderstood what was being asked, especially when it came to identifying key terms or conditions. I also sometimes rushed through programming logic or assumptions, which led to incorrect conclusions. To improve, I plan to take extra care in reading each question carefully, paying close attention to the small but important details, and avoiding assumptions based on incomplete information.
  </p>
</div>

# Sprint 3 code snippet

    /**
     * Fetch posts based on selected channel
     * Handle response: Fetch and display posts
     */
    async function fetchData(channelId) {
        try {
            const response = await fetch(`${pythonURI}/api/posts/filter`, {
                ...fetchOptions,
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify({ channel_id: channelId })
            });
            if (!response.ok) {
                throw new Error('Failed to fetch posts: ' + response.statusText);
            }

            // Parse the JSON data
            const postData = await response.json();

            // Extract posts count
            const postCount = postData.length || 0;

            // Update the HTML elements with the data
            document.getElementById('count').innerHTML = `<h2>Count ${postCount}</h2>`;

            // Get the details div
            const detailsDiv = document.getElementById('details');
            detailsDiv.innerHTML = ''; // Clear previous posts

            // Iterate over the postData and create HTML elements for each item
            postData.forEach(postItem => {
                const postElement = document.createElement('div');
                postElement.className = 'post-item';
                postElement.innerHTML = `
                    <h3>${postItem.title}</h3>
                    <p><strong>Channel:</strong> ${postItem.channel_name}</p>
                    <p><strong>User:</strong> ${postItem.user_name}</p>
                    <p>${postItem.comment}</p>
                `;
                detailsDiv.appendChild(postElement);
            });

        } catch (error) {
            console.error('Error fetching data:', error);
        }
    }

    // Fetch groups when the page loads
    fetchGroups();
</script>

<div style="background-color: #d0ebf5; padding: 20px; border-radius: 10px; border: 2px solid #91cbe1;">
    <h3 style="font-size: 18px; color: #3a7b9e; font-family: 'Times New Roman', serif; font-weight: bold;">
        Explanation of Code
    </h3>
    <ul style="font-size: 16px; color: #3a7b9e; font-family: 'Times New Roman', serif;">
        <li>The function <strong>fetchData(channelId)</strong> retrieves posts associated with a specific channel using the channel's ID.</li>
        <li>It sends an asynchronous POST request to the API endpoint with the channel ID in the request body.</li>
        <li>After receiving a response, it checks if the request was successful; if not, it throws an error.</li>
        <li>The JSON data from the response is parsed, and the total count of posts is extracted and displayed on the page.</li>
        <li>It clears the previous content in the "details" section and dynamically creates new elements for each post, displaying the post title, channel name, user, and comment.</li>
        <li>Errors during the fetch process are caught and logged in the console for debugging purposes.</li>
    </ul>
</div>


<!-- Plan of Action Section -->
<div style="margin-top: 20px; background-color: #e8f5e9; padding: 15px; border-radius: 10px;">
    <h2 style="color: #2e7d32; font-family: 'Times New Roman', sans-serif;">Plan of Action to Improve My AP CSP Exam Score</h2>
    <p style="font-size: 18px; color: #1b5e20;">
        <strong>Understand Key Concepts:</strong>
        <ul style="margin-left: 20px;">
            <li>Review programming fundamentals, algorithms, and data analysis.</li>
            <li>Utilize AP CSP prep books, online resources, and classroom notes.</li>
        </ul>
        <strong>Practice Multiple-Choice Questions:</strong>
        <ul style="margin-left: 20px;">
            <li>Complete past AP CSP exam questions for familiarity with question patterns.</li>
            <li>Use timed quizzes to simulate test conditions.</li>
        </ul>
        <strong>Focus on the Create Performance Task:</strong>
        <ul style="margin-left: 20px;">
            <li>Follow the rubric carefully to meet all requirements.</li>
            <li>Test and debug the program thoroughly.</li>
            <li>Document the development process clearly and concisely.</li>
        </ul>
        <strong>Develop a Study Schedule:</strong>
        <ul style="margin-left: 20px;">
            <li>Dedicate time daily to review concepts and practice tasks.</li>
            <li>Alternate between multiple-choice and performance tasks for balanced preparation.</li>
        </ul>
        <strong>Seek Feedback and Guidance:</strong>
        <ul style="margin-left: 20px;">
            <li>Discuss doubts with teachers or peers.</li>
            <li>Get feedback on Create Task drafts to improve quality.</li>
        </ul>
        <strong>Simulate Full Exams:</strong>
        <ul style="margin-left: 20px;">
            <li>Take practice exams under timed conditions to build confidence.</li>
            <li>Analyze mistakes and address weak areas.</li>
        </ul>
    </p>
</div>



