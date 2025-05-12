
<!DOCTYPE html>
<html lang="uz">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Qidiruv Sahifasi</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f2f2f2;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      margin: 0;
    }

    h1 {
      color: #333;
      margin-bottom: 30px;
    }

    .search-box {
      background: white;
      padding: 20px 30px;
      border-radius: 12px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    }

    input[type="text"] {
      width: 300px;
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 8px;
      font-size: 16px;
    }

    button {
      padding: 10px 20px;
      margin-left: 10px;
      background-color: #4285f4;
      color: white;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      font-size: 16px;
    }

    button:hover {
      background-color: #3367d6;
    }

    select {
      margin-top: 10px;
      padding: 8px;
      border-radius: 8px;
      font-size: 14px;
    }
  </style>
</head>
<body>
  <h1>Oddiy Qidiruv Sayti</h1>
  <div class="search-box">
    <input type="text" id="searchInput" placeholder="Bu yerga yozing..." />
    <button onclick="search()">Qidirish</button>
    <br><br>
    <select id="engine">
      <option value="google">Google</option>
      <option value="yandex">Yandex</option>
      <option value="bing">Bing</option>
    </select>
  </div>

  <script>
    function search() {
      const query = document.getElementById('searchInput').value.trim();
      const engine = document.getElementById('engine').value;
      if (!query) return alert("Iltimos, qidiruv so'zini kiriting!");

      let url = "";

      switch (engine) {
        case "google":
          url = `https://www.google.com/search?q=${encodeURIComponent(query)}`;
          break;
        case "yandex":
          url = `https://yandex.com/search/?text=${encodeURIComponent(query)}`;
          break;
        case "bing":
          url = `https://www.bing.com/search?q=${encodeURIComponent(query)}`;
          break;
      }

      window.open(url, '_blank');
    }
  </script>
</body>
</html>
