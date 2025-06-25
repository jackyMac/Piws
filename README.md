from zipfile import ZipFile
from pathlib import Path

# 创建 HTML 文件内容
html_content = '''<!DOCTYPE html>
<html lang="zh">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Piws | BRC-20 铭文官网</title>
  <style>
    body {
      font-family: "Segoe UI", Roboto, sans-serif;
      background: linear-gradient(to right, #0d1117, #161b22);
      color: #ffffff;
      margin: 0;
      padding: 2rem;
    }
    .container {
      max-width: 800px;
      margin: auto;
    }
    h1 {
      font-size: 3rem;
      color: #f7931a;
    }
    .highlight {
      color: #00ffc8;
    }
    .section {
      margin-top: 2rem;
    }
    .logo {
      width: 100px;
      height: 100px;
    }
    .footer {
      margin-top: 3rem;
      text-align: center;
      font-size: 0.9rem;
      color: #888;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>🪙 Piws <span class="highlight">BRC-20</span> Token</h1>
    <p>🚀 Inspired by Pi Network & Bitcoin Ordinals</p>

    <div class="section">
      <h2>📌 项目信息 / Project Info</h2>
      <ul>
        <li><strong>Tick：</strong> PIWS</li>
        <li><strong>协议：</strong> BRC-20（基于比特币）</li>
        <li><strong>发行量：</strong> 21,000,000 Piws</li>
        <li><strong>每次铸造上限：</strong> 1,000</li>
        <li><strong>部署地址：</strong> 社区部署</li>
      </ul>
    </div>

    <div class="section">
      <h2>🌐 项目简介 / Introduction</h2>
      <p>
        Piws 是一个由 Pi 社区驱动的铭文项目，融合了 Pi 精神与 BRC-20 创新。旨在成为跨链生态中的先驱铭文资产。
      </p>
      <p>
        Piws is a community-powered BRC-20 inscription symbolizing freedom, fairness, and digital pioneers. Born from the Pi Network ethos.
      </p>
    </div>

    <div class="section">
      <h2>🛠 功能亮点 / Key Features</h2>
      <ul>
        <li>✔️ 完全链上部署</li>
        <li>✔️ 无预挖 / 无私募 / 无团队分配</li>
        <li>✔️ 社区参与式铸造</li>
        <li>✔️ 可作为未来 DEX 资产</li>
      </ul>
    </div>

    <div class="section">
      <h2>🔗 探索与上架 / Listings</h2>
      <p>
        即将上线：UniSat, OKX Web3, Binance Web3, Bitget Wallet 等平台。
      </p>
    </div>

    <div class="footer">
      &copy; 2025 Piws Team. Powered by Pi Network Hackers.
    </div>
  </div>
</body>
</html>'''

# 保存 HTML 文件
html_path = Path("/mnt/data/index.html")
html_path.write_text(html_content, encoding='utf-8')

# 创建 zip 文件
zip_path = Path("/mnt/data/piws_site.zip")
with ZipFile(zip_path, 'w') as zipf:
    zipf.write(html_path, arcname="index.html")

zip_path
