# updata
<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>بررسی آپدیت موبایل 📱</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: #f0f4f8;
            padding: 20px;
            line-height: 1.6;
        }
        .container {
            max-width: 800px;
            margin: 0 auto;
            background: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 0 20px rgba(0,0,0,0.1);
        }
        h1 { color: #2c3e50; }
        .info-box {
            background: #e8f4fc;
            padding: 15px;
            border-radius: 10px;
            margin: 20px 0;
        }
        a {
            color: #3498db;
            text-decoration: none;
            font-weight: bold;
        }
        a:hover { text-decoration: underline; }
    </style>
</head>
<body>
    <div class="container">
        <h1>بررسی وضعیت موبایل شما 📱</h1>
        
        <div id="device-info" class="info-box">
            <h3>در حال تشخیص دستگاه...</h3>
        </div>

        <div id="update-info" class="info-box">
            <h3>بررسی آپدیت سیستم عامل...</h3>
        </div>

        <div id="rom-sites" class="info-box">
            <h3>سایت های معتبر برای آپدیت ROM:</h3>
            <ul>
                <li><a href="https://www.xda-developers.com" target="_blank">XDA Developers (برای همه دستگاه‌ها)</a></li>
                <li><a href="https://www.sammobile.com" target="_blank">Sammobile (برای سامسونگ)</a></li>
                <li><a href="https://miuirom.org" target="_blank">MIUI Downloads (برای شیائومی)</a></li>
            </ul>
        </div>
    </div>

    <script>
        // تشخیص اطلاعات دستگاه
        const deviceInfo = {
            os: navigator.userAgent.match(/Android|iPhone|iPad|iPod|Windows Phone/i)[0] || 'ناشناخته',
            osVersion: navigator.userAgent.match(/Android\s\d+|OS\s\d+/i)?.[0] || 'ناشناخته',
            model: navigator.userAgent.match(/; (\w+)\sBuild/i)?.[1] || 'ناشناخته'
        };

        // نمایش اطلاعات
        document.getElementById('device-info').innerHTML = `
            <h3>📱 مشخصات دستگاه شما:</h3>
            <p>سیستم عامل: ${deviceInfo.os}</p>
            <p>نسخه سیستم عامل: ${deviceInfo.osVersion}</p>
            <p>مدل دستگاه: ${deviceInfo.model}</p>
        `;

        // لینک آپدیت بر اساس سیستم عامل
        const updateLinks = {
            Android: 'https://www.google.com/android/find',
            iPhone: 'https://support.apple.com/ios/update',
            iPad: 'https://support.apple.com/ios/update',
            Windows_Phone: 'https://support.microsoft.com/windows'
        };

        document.getElementById('update-info').innerHTML = `
            <h3>🔍 آخرین آپدیت سیستم عامل:</h3>
            <p>برای بررسی آپدیت رسمی، به لینک زیر مراجعه کنید:</p>
            <a href="${updateLinks[deviceInfo.os] || '#'}" target="_blank">
                ${deviceInfo.os === 'Android' ? 'بررسی آپدیت اندروید' : 'بررسی آپدیت iOS'}
            </a>
        `;
    </script>
</body>
</html>
