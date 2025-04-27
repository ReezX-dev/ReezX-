<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Minecraft Java.apk - Mediafire</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f2f4f8;
      margin: 0;
      padding: 0;
      display: flex;
      flex-direction: column;
      align-items: center;
    }
    .container {
      background: white;
      margin-top: 50px;
      padding: 20px;
      width: 90%;
      max-width: 600px;
      box-shadow: 0 2px 10px rgba(0,0,0,0.2);
      border-radius: 8px;
      text-align: center;
      position: relative;
    }
    .logo {
      width: 180px;
      margin-bottom: 20px;
    }
    .file-info {
      margin-bottom: 20px;
    }
    .file-name {
      font-size: 20px;
      font-weight: bold;
      color: #333;
    }
    .file-size {
      color: #666;
      margin-top: 5px;
    }
    .download-btn {
      display: inline-block;
      background: #00b0f4;
      color: white;
      padding: 12px 30px;
      border-radius: 6px;
      text-decoration: none;
      font-size: 18px;
      margin-top: 20px;
      cursor: pointer;
    }
    .download-btn:hover {
      background: #0090cc;
    }
    .ad {
      margin-top: 30px;
      font-size: 12px;
      color: #aaa;
    }
    .loading-section {
      display: none;
      margin-top: 20px;
      width: 100%;
    }
    .progress-bar {
      width: 100%;
      background-color: #ddd;
      border-radius: 10px;
      overflow: hidden;
    }
    .progress-bar-fill {
      height: 20px;
      width: 0%;
      background-color: #00b0f4;
      transition: width 0.3s;
    }
    .download-status {
      margin-top: 10px;
      font-size: 16px;
      color: #333;
    }
    .notification {
      display: none;
      position: absolute;
      top: -20px;
      background: #4CAF50;
      color: white;
      padding: 8px 20px;
      border-radius: 20px;
      font-size: 14px;
      box-shadow: 0px 2px 8px rgba(0,0,0,0.3);
      animation: fadeIn 1s forwards;
    }
    @keyframes fadeIn {
      from {opacity: 0;}
      to {opacity: 1;}
    }
  </style>
</head>
<body>

<div class="container">
  <div id="notif" class="notification">Download Complete!</div>

  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/7/7e/MediaFire_logo.svg/512px-MediaFire_logo.svg.png" class="logo" alt="Mediafire Logo">

  <div class="file-info">
    <div class="file-name">Minecraft Java.apk</div>
    <div class="file-size">2 GB</div>
  </div>

  <button class="download-btn" onclick="startDownload()">Download</button>

  <div class="loading-section" id="loadingSection">
    <div class="progress-bar">
      <div class="progress-bar-fill" id="progressFill"></div>
    </div>
    <div class="download-status" id="downloadStatus">0 KB / 2048000 KB</div>
  </div>

  <div class="ad">*Note: Ini hanya simulasi, file tidak benar-benar tersedia.</div>
</div>

<script>
function startDownload() {
  const btn = document.querySelector('.download-btn');
  const loading = document.getElementById('loadingSection');
  const fill = document.getElementById('progressFill');
  const status = document.getElementById('downloadStatus');
  const notif = document.getElementById('notif');
  
  btn.style.display = 'none';
  loading.style.display = 'block';

  let downloaded = 0;
  let total = 2048000; // 2GB = 2.048.000KB
  let speed = 15000; // real: 1,5 KB per detik, simulasi: 15 KB per detik biar ga kelamaan
  let intervalTime = 1000; // 1 detik

  const interval = setInterval(() => {
    downloaded += speed;
    if (downloaded >= total) {
      downloaded = total;
      clearInterval(interval);
      status.innerHTML = "2048000 KB / 2048000 KB";
      fill.style.width = "100%";
      notif.style.display = "block";
    } else {
      status.innerHTML = `${downloaded} KB / 2048000 KB`;
      let percent = (downloaded / total) * 100;
      fill.style.width = percent + "%";
    }
  }, intervalTime);
}
</script>

</body>
</html>
