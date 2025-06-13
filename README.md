<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Add New Topic - PulseTechnica</title>
  <style>
    body {
      font-family: Arial;
      padding: 20px;
      background-color: #f0f0f0;
    }
    h1 {
      color: #333;
    }
    input, textarea {
      width: 100%;
      padding: 10px;
      margin-top: 10px;
      font-size: 16px;
    }
    button {
      margin-top: 10px;
      padding: 10px 20px;
      font-size: 16px;
      background-color: #007bff;
      color: white;
      border: none;
      cursor: pointer;
    }
    #output {
      margin-top: 30px;
      background: #fff;
      padding: 15px;
      border-radius: 5px;
    }
  </style>
</head>
<body>
  <h1>Add New Topic</h1>
  <input type="text" id="title" placeholder="Enter topic title" />
  <textarea id="content" rows="6" placeholder="Write your topic here..."></textarea>
  <button onclick="addTopic()">Add Topic</button>

  <div id="output"></div>

  <script>
    function addTopic() {
      const title = document.getElementById('title').value;
      const content = document.getElementById('content').value;

      if (title && content) {
        const output = document.getElementById('output');
        const newArticle = `
          <article style="border-top:1px solid #ccc; margin-top:20px; padding-top:10px;">
            <h2>${title}</h2>
            <p>${content}</p>
          </article>`;
        output.innerHTML += newArticle;

        // Clear form
        document.getElementById('title').value = '';
        document.getElementById('content').value = '';
      } else {
        alert("Please fill in both title and content.");
      }
    }
  </script>
</body>
</html>

