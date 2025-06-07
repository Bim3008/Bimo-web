<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Pertanyaan Seru</title>
  <style>
    body {
      font-family: sans-serif;
      background: linear-gradient(to right, #ffecd2, #fcb69f);
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 50px;
    }
    h1 {
      color: #333;
    }
    input, button {
      padding: 10px;
      margin-top: 20px;
      font-size: 16px;
    }
    button {
      background-color: #333;
      color: white;
      border: none;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <h1>Apa makanan favorit kamu?</h1>
  <input type="text" id="jawaban" placeholder="Tulis jawaban di sini" />
  <button onclick="simpanJawaban()">Kirim Jawaban</button>

  <script>
    function simpanJawaban() {
      const jawab = document.getElementById('jawaban').value;
      if(jawab.trim() !== "") {
        let data = JSON.parse(localStorage.getItem("jawabanOrang") || "[]");
        data.push(jawab);
        localStorage.setItem("jawabanOrang", JSON.stringify(data));
        alert("Jelek bgt selera makan lu");
        document.getElementById('jawaban').value = "";
      } else {
        alert("Isi dulu dong jawabannya!");
      }
    }
  </script>
</body>
</html>
