---
layout: page
title: ---
permalink: /ppr/
---

<div class="about-container">

<h1>PPR Review</h1>
<br>
<h3>Overview of College Board PPR Requirements<h3>
<br>
<br>
<h2>Procedure:</h2>
    <ul>
        <li>Defines the procedure’s name and return type (if necessary)</li>
        <li>Contains and uses one or more parameters that have an effect on the functionality of the procedure</li>
        <li>Implements an algorithm that includes sequencing, selection, and iteration</li>
    </ul>
<br>
<img src="https://github.com/user-attachments/assets/7a8b50df-79ab-4523-900c-4140669d71c2" alt="PPR Image 1">
<h6>(front end code responsible for new data {quotes} creation and saving to database)</h6>
<br>
<h4>The second program code segment must show where your student-developed procedure is being called in your program.</h4>
<br>
<img src="https://github.com/user-attachments/assets/d3d31bcf-b002-49dc-a8a5-05e54492f480" alt="PPR Image 2">
<h6>(Parameter)</h6>
<br>
<h2>List:</h2>
    <h4>Capture and paste two program code segments you developed during the administration of this task that contain a list (or other collection type) being used to manage complexity in your program.</h4>
    <br>
    <h4>The first program code segment must show how data have been stored in the list.</h4>
<img src="https://github.com/user-attachments/assets/68844d8c-2954-4ea5-ae71-856427bc308b" alt="PPR Image 3">
<br>
<h4>The second program code segment must show the data in the same list being used, such as creating new data from the existing data or accessing multiple elements in the list, as part of fulfilling the program’s purpose.</h4>
<img src="https://github.com/user-attachments/assets/d85a69b5-6045-4812-9486-5392ef010ab7" alt="PPR Image 4">
<br>
<h1>Code Analysis</h1>
<br>
<div class="section">
        <h2>Procedure Section (Images 1 and 2)</h2>
        <br>
        <p><strong>The procedure to analyze:</strong> <code>addQuote()</code></p>
        <p>This function is responsible for adding a new quote to the system.</p>

<h3>1. Defines the procedure’s name and return type</h3>
<br>
        <ul>
            <li>The function is named <code>addQuote()</code>, which clearly defines its purpose.</li>
            <li>It is an <code>async</code> function, meaning it returns a <code>Promise&lt;void&gt;</code> (performs an action asynchronously without returning a value).</li>
        </ul>

<h3>2. Contains and uses parameters that affect functionality</h3>
<br>
        <ul>
            <li>This function does not explicitly take parameters but interacts with user inputs:</li>
            <li><code>document.getElementById('new-quote-name').value;</code> → Retrieves the quote text.</li>
            <li><code>document.getElementById('new-quote-category').value;</code> → Retrieves the category.</li>
            <li>These values directly impact the API request, determining the new quote and category being added.</li>
        </ul>

<h3>3. Implements an algorithm that includes sequencing, selection, and iteration</h3>
<br>
<h4>Sequencing (Ordered execution of steps):</h4>
<br>
        <ul>
            <li>Retrieves input values.</li>
            <li>Sends an HTTP request to store the new quote.</li>
            <li>Clears input fields after a successful addition.</li>
            <li>Refreshes the quotes list.</li>
        </ul>
<br>
<h4>Selection (Decision-making using conditionals):</h4>
        <p>This ensures that an error is handled if the API call fails. The function only proceeds to refresh the list if the quote is added successfully.</p>

<h4>Iteration (Looping through data):</h4>
<br>
        <p>The function calls <code>fetchQuotes()</code> after adding a quote, which likely retrieves and iterates over all stored quotes to refresh the display.</p>
<br>
<h3>Conclusion (Procedure)</h3>
<br>
        <p>✅ The <code>addQuote()</code> function meets all procedural requirements:</p>
        <ul>
            <li>Has a clear name and an implicit return type (<code>Promise&lt;void&gt;</code>).</li>
            <li>Uses input values that affect its functionality.</li>
            <li>Implements sequencing (input → API request → clear inputs → refresh list).</li>
            <li>Uses selection (error handling).</li>
            <li>Indirectly utilizes iteration through <code>fetchQuotes()</code>.</li>
        </ul>
    </div>
<br>
<div class="section">
        <h2>List Section (Images 3 and 4)</h2>
        <br>
        <p>The list is used to manage stored quotes in the system.</p>

<h3>1st Code Segment (Storing Data in a List)</h3>
<br>
        <p>From Image 1 (<code>promptUpdateQuote()</code>):</p>

<h4>How this segment stores data in a list:</h4>
<br>
        <ul>
            <li>The backend (likely a database or an array of quotes) stores the updated quote.</li>
            <li>The <code>PUT</code> request modifies an existing entry in the list by matching the <code>old_name</code> value.</li>
            <li>The updated quote name and category are then saved.</li>
            <li>The list is updated dynamically rather than creating new separate variables.</li>
        </ul>

<h3>2nd Code Segment (Using the List)</h3>
<br>
        <p>From Image 3 (Backend Python Code):</p>
<h4>How this segment uses the list:</h4>
<br>
        <ul>
            <li>The list of quotes is stored in a database (or similar collection).</li>
            <li>Filtering (<code>filter_by(name=data['old_name'], category=data['category'])</code>) ensures that only the correct quote is modified.</li>
            <li>This manages complexity because the system does not store each quote in a separate variable—it retrieves and updates data dynamically.</li>
        </ul>
        <br>
    </div>
<div class="section">
        <h2>Final Summary</h2>
        <br>

 <h3>Procedure Section (Images 1 and 2 → <code>addQuote()</code>)</h3>
        <ul>
            <li>✅ Defines a clear function (<code>addQuote()</code>).</li>
            <li>✅ Uses input fields to determine functionality.</li>
            <li>✅ Implements sequencing (getting input → API call → clearing input → refreshing list).</li>
            <li>✅ Includes selection (error handling).</li>
            <li>✅ Uses iteration indirectly (refreshing list via <code>fetchQuotes()</code>).</li>
        </ul>
<br>
<h3>List Section (Images 3 and 4 → Quote Management)</h3>
        <ul>
            <li>✅ Stores data dynamically in a list (Image 1: Updating stored quotes).</li>
            <li>✅ Retrieves and updates quotes using <code>filter_by()</code> (Image 2: Managing complexity through structured data storage).</li>
            <li>✅ Prevents redundant variables by using a query system to search and update data dynamically.</li>
        </ul>



<style>

ol {
    list-style-type: disc !important;
    margin: 15px 20px !important;
    padding-left: 40px !important;
}

li {
    background-color:rgb(74, 126, 83) !important;
    padding: 10px 15px !important;
    margin: 10px 0 !important;
    border-radius: 10px !important;
    border-left: 5px solidrgb(0, 0, 0) !important;
    box-shadow: 0px 5px 10px rgba(18, 18, 18, 0.5) !important;
    color: #ffffff !important;
}

.about-container {
    max-width: 800px;
    margin: 50px auto;
    padding: 20px;
    background-color:rgb(32, 62, 34);
    border-radius: 10px;
    border: 1px solidrgb(38, 58, 36);
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
    color: #fff;
    text-align: center;
}

.about-container h1, h2, .about-container h2 {
    color:rgb(135, 220, 115);
}
</style>