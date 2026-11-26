
<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>StudyMaker AI</title>
  <style>
    body {
      font-family: sans-serif;
      background: #f3f6fc;
      margin: 0;
      padding: 30px 15px;
      color: #26334a;
    }

    .container {
      max-width: 600px;
      margin: auto;
      background: white;
      padding: 30px;
      border-radius: 18px;
      box-shadow: 0 4px 20px #0001;
    }

    h1 {
      text-align: center;
      color: #2563eb;
    }

    .description {
      text-align: center;
      color: #64748b;
    }

    .upload {
      display: block;
      padding: 30px;
      margin: 25px 0;
      border: 2px dashed #93b4ee;
      border-radius: 12px;
      text-align: center;
      cursor: pointer;
    }

    button {
      width: 100%;
      padding: 15px;
      background: #2563eb;
      color: white;
      border: none;
      border-radius: 10px;
      font-size: 16px;
      cursor: pointer;
    }

    button:hover {
      background: #1d4ed8;
    }

    #preview {
      width: 100%;
      margin-top: 15px;
      border-radius: 10px;
      display: none;
    }

    #status {
      text-align: center;
      margin-top: 15px;
    }
  </style>
</head>
<body>

  <div class="container">
    <h1>StudyMaker AI</h1>
    <p class="description">
      教科書から自分だけの問題集を作ろう！
    </p>

    <h3>① 教科書の写真を選択</h3>

    <label class="upload">
      📷 写真を選ぶ
      <input
        type="file"
        id="photo"
        accept="image/*"
        hidden
      >
    </label>

    <img id="preview">

    <h3>② 問題数</h3>
    <select id="count">
      <option>5問</option>
      <option>10問</option>
      <option>20問</option>
    </select>

    <h3>③ 難易度</h3>
    <select id="level">
      <option>基礎</option>
      <option selected>標準</option>
      <option>応用</option>
    </select>

    <br><br>

    <button onclick="generate()">
      問題を生成する
    </button>

    <p id="status"></p>
  </div>

  <script>
    const photo = document.getElementById("photo");
    const preview = document.getElementById("preview");

    photo.addEventListener("change", function() {
      const file = photo.files[0];

      if (file) {
        preview.src = URL.createObjectURL(file);
        preview.style.display = "block";
      }
    });

    function generate() {
      if (!photo.files[0]) {
        document.getElementById("status").textContent =
          "先に写真を選んでね！";
        return;
      }

      document.getElementById("status").textContent =
        "写真を受け取りました！AI機能はこれから実装します。";
    }
  </script>

</body>
</html>
# studymaker-ai
 AI-powered textbook practice generator 
