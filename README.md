from pathlib import Path
import zipfile

root = Path("/mnt/data/best_gravity")
root.mkdir(exist_ok=True)

html = """<!doctype html>
<html lang="hi">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>Best Gravity</title>
<style>
*{box-sizing:border-box}body{margin:0;font-family:Arial,sans-serif;background:#0b1020;color:#fff}
nav{display:flex;justify-content:space-between;align-items:center;padding:18px 7%;background:#111936;position:sticky;top:0}
.logo{font-size:25px;font-weight:800}.links a{color:#fff;text-decoration:none;margin-left:20px}
.hero{text-align:center;padding:100px 20px;background:linear-gradient(135deg,#111936,#253a72)}
h1{font-size:52px;margin:10px 0}.hero p{font-size:20px;color:#dce5ff}.btn{display:inline-block;margin-top:20px;padding:13px 24px;border-radius:30px;background:#fff;color:#17244d;text-decoration:none;font-weight:700}
section{padding:65px 7%;text-align:center}.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:20px}
.card{background:#151e3d;padding:28px;border-radius:18px}.card h3{margin-top:0}
footer{text-align:center;padding:30px;background:#070b18;color:#aeb9d9}
@media(max-width:600px){h1{font-size:38px}.links a{margin-left:8px;font-size:13px}}
</style>
</head>
<body>
<nav><div class="logo">Best Gravity</div><div class="links"><a href="#home">Home</a><a href="#about">About</a><a href="#services">Services</a><a href="#contact">Contact</a></div></nav>
<section class="hero" id="home"><h1>Best Gravity</h1><p>आपकी डिजिटल दुनिया का एक शानदार अनुभव।</p><a class="btn" href="#services">Explore</a></section>
<section id="about"><h2>हमारे बारे में</h2><p>Best Gravity एक modern और mobile-friendly वेबसाइट है, जिसे आपकी जरूरत के अनुसार बदला जा सकता है।</p></section>
<section id="services"><h2>हमारी Services</h2><div class="grid"><div class="card"><h3>Web Design</h3><p>Modern और responsive design.</p></div><div class="card"><h3>Creative Ideas</h3><p>आपके brand के लिए आकर्षक presentation.</p></div><div class="card"><h3>Support</h3><p>आगे वेबसाइट को आसानी से update करें.</p></div></div></section>
<section id="contact"><h2>Contact</h2><p>अपना ईमेल और संपर्क जानकारी यहाँ जोड़ें।</p></section>
<footer>© 2026 Best Gravity. All rights reserved.</footer>
</body>
</html>"""

(root/"index.html").write_text(html, encoding="utf-8")
zip_path = Path("/mnt/data/Best_Gravity_Website.zip")
with zipfile.ZipFile(zip_path, "w", zipfile.ZIP_DEFLATED) as z:
    z.write(root/"index.html", "index.html")

print(f"तैयार है: {zip_path}")

