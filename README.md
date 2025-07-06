# netli
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8">
  <title>منشورات بسيطة</title>
  <style>
    body {
      font-family: sans-serif;
      background-color: #f4f4f4;
      padding: 20px;
      max-width: 600px;
      margin: auto;
    }
    textarea {
      width: 100%;
      height: 100px;
      font-size: 16px;
      padding: 10px;
      resize: vertical;
    }
    button {
      margin-top: 10px;
      padding: 10px 20px;
      font-size: 16px;
      cursor: pointer;
      background-color: #4CAF50;
      color: white;
      border: none;
      border-radius: 5px;
    }
    .post {
      background-color: white;
      padding: 15px;
      margin-top: 15px;
      border-radius: 8px;
      box-shadow: 0 0 5px rgba(0,0,0,0.1);
    }
    .timestamp {
      font-size: 12px;
      color: gray;
      margin-top: 5px;
    }
  </style>
</head>
<body>

  <h2>منشورات الزوار</h2>

  <textarea id="postInput" placeholder="اكتب هنا..."></textarea>
  <button onclick="addPost()">نشر</button>

  <div id="postsContainer"></div>

  <script>
    const postsContainer = document.getElementById('postsContainer');

    function addPost() {
      const input = document.getElementById('postInput');
      const text = input.value.trim();

      if (text === '') return;

      const postElement = document.createElement('div');
      postElement.className = 'post';

      const timestamp = new Date().toLocaleString('ar-EG');

      postElement.innerHTML = `
        <div>${text}</div>
        <div class="timestamp">📅 ${timestamp}</div>
      `;

      postsContainer.prepend(postElement); // يظهر الأحدث في الأعلى
      input.value = '';
    }
  </script>

</body>
</html>
