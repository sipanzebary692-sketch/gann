<!DOCTYPE html>
<html lang="ku" dir="rtl">
<head>
    <meta charset="UTF-8">
    <title>Gann Empire - Fixed Telegram</title>
    <style>
        body { font-family: sans-serif; background: #05070a; color: white; text-align: center; padding: 20px; }
        .card { background: #0f121a; padding: 20px; border-radius: 15px; border: 1px solid #1e272e; max-width: 500px; margin: auto; }
        button { background: #00a8ff; color: white; border: none; padding: 15px 30px; border-radius: 8px; cursor: pointer; font-weight: bold; font-size: 16px; }
        #status { margin-top: 20px; color: #f1c40f; }
    </style>
</head>
<body>

<div class="card">
    <h2>تاقیکردنەوەی تێلیگرام</h2>
    <p>ئایدی تۆ: 1397344355</p>
    <button onclick="testNow()">کلیک بکە بۆ ناردنی نامە</button>
    <div id="status">ئامادەیە بۆ تاقیکردنەوە</div>
</div>

<script>
    const token = "8666790930:AAGP2IRbkeDPv1PX66oZ9cNJl3Pw63j10ww";
    const chat = "1397344355";

    function testNow() {
        const msg = "✅ سڵاو! کۆدە نوێیەکە کار دەکات و بەستراوەتەوە.";
        const url = https://api.telegram.org/bot${token}/sendMessage?chat_id=${chat}&text=${encodeURIComponent(msg)};
        
        document.getElementById('status').innerText = "خەریکە دەنێردرێت...";

        // بەکارهێنانی شێوازێکی کۆنتر بەڵام جێگیرتر بۆ ناردن
        var xhr = new XMLHttpRequest();
        xhr.open("GET", url, true);
        xhr.onreadystatechange = function() {
            if (xhr.readyState == 4) {
                if (xhr.status == 200) {
                    document.getElementById('status').innerText = "✅ نامەکە بە سەرکەوتوویی نێردرا! سەیری تێلیگرام بکە.";
                    document.getElementById('status').style.color = "#00d2d3";
                } else {
                    document.getElementById('status').innerText = "❌ هەڵە ڕوویدا: " + xhr.status;
                    document.getElementById('status').style.color = "#ff4d4d";
                    console.log(xhr.responseText);
                }
            }
        };
        xhr.send();
    }
</script>

</body>
</html>
