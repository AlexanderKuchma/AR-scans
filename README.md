<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AR Object Viewer</title>
    <script>
        function getMobileOperatingSystem() {
            const userAgent = navigator.userAgent || navigator.vendor || window.opera;

            // iOS detection
            if (/iPad|iPhone|iPod/.test(userAgent) && !window.MSStream) {
                return 'iOS';
            }

            // Android detection
            if (/android/i.test(userAgent)) {
                return 'Android';
            }

            return 'unknown';
        }

        function redirectToARFile() {
            const os = getMobileOperatingSystem();

            if (os === 'iOS') {
                // Redirect to USDZ file for iOS
                window.location.href = 'https://github.com/AlexanderKuchma/AR-scans/raw/main/Scaniverse%202024-07-15%20170330.usdz';
            } else if (os === 'Android') {
                // Redirect to GLB file for Android
                window.location.href = 'https://github.com/AlexanderKuchma/AR-scans/raw/main/Scaniverse%202024-07-15%20170330.usdz';
            } else {
                alert('Your device is not supported for AR viewing.');
            }
        }

        window.onload = redirectToARFile;
    </script>
</head>
<body>
    <h1>Redirecting to AR Object...</h1>
</body>
</html>
