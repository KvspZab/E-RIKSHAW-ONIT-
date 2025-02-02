<!DOCTYPE html>
<html lang="hi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ई रिक्शा पंजीकरण</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #5fadac;
            background-image: 
                radial-gradient(circle at 100% 100%, rgba(255,255,255,0.1) 0%, transparent 50%),
                radial-gradient(circle at 0% 0%, rgba(255,255,255,0.1) 0%, transparent 50%);
            margin: 0;
            padding: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
        }
        .container {
            background-color: white;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
            width: 100%;
            max-width: 500px;
            position: relative;
            overflow: hidden;
        }
        .container::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: 
                linear-gradient(45deg, rgba(95, 173, 172, 0.05) 25%, transparent 25%),
                linear-gradient(-45deg, rgba(95, 173, 172, 0.05) 25%, transparent 25%),
                linear-gradient(45deg, transparent 75%, rgba(95, 173, 172, 0.05) 75%),
                linear-gradient(-45deg, transparent 75%, rgba(95, 173, 172, 0.05) 75%);
            background-size: 20px 20px;
            pointer-events: none;
            z-index: 1;
        }
        .form-content {
            position: relative;
            z-index: 2;
        }
        .logo {
            text-align: center;
            margin-bottom: 20px;
        }
        .logo img {
            max-width: 200px;
            height: auto;
        }
        h1 {
            text-align: center;
            color: #333;
            margin-bottom: 10px;
        }
        .description {
            text-align: center;
            margin-bottom: 30px;
            padding: 15px;
            background-color: rgba(95, 173, 172, 0.1);
            border-radius: 6px;
            line-height: 1.6;
            color: #444;
        }
        form {
            display: flex;
            flex-direction: column;
        }
        label {
            margin-top: 10px;
            font-weight: bold;
        }
        input, select {
            width: 100%;
            padding: 8px;
            margin-top: 5px;
            border: 1px solid #ddd;
            border-radius: 4px;
            box-sizing: border-box;
        }
        input[type="file"] {
            border: none;
        }
        input[type="checkbox"] {
            width: auto;
            margin-right: 10px;
        }
        button {
            background-color: #5fadac;
            color: white;
            padding: 10px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            margin-top: 20px;
            font-weight: bold;
            transition: background-color 0.3s ease;
        }
        button:hover {
            background-color: #4f9290;
        }
        button:disabled {
            background-color: #cccccc;
            cursor: not-allowed;
        }
        .checkbox-container {
            display: flex;
            align-items: center;
            margin-top: 10px;
        }
        @media (max-width: 600px) {
            .container {
                padding: 20px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="form-content">
            <div class="logo">
                <img src="https://hebbkx1anhila5yf.public.blob.vercel-storage.com/logo%20evrything%20onit.jpg-oWXuvz2PWvP8dvDJEGHI7z83v4APei.jpeg" alt="ONIT Logo">
            </div>
            <h1>ई रिक्शा पंजीकरण</h1>
            <div class="description">
                महाकुंभ के इस पावन पर्व में आरटीओ प्रयागराज के सहयोग से हम आपको ऑनलाइन सेवा बुकिंग का अवसर प्रदान कर रहे हैं। आपसे निवेदन है कि इस अवसर का लाभ उठाएं और श्रद्धालुओं को बेहतर सेवा प्रदान करने में योगदान दें। इसके लिए आप नीचे दिए गए फॉर्म को भरकर स्वयं को OniT पर रजिस्टर करें।
            </div>
            <form id="serviceProviderForm">
                <label for="name">नाम:</label>
                <input type="text" id="name" name="name" required>

                <label for="vehicleType">वाहन का प्रकार:</label>
                <select id="vehicleType" name="vehicleType" required>
                    <option value="">वाहन का प्रकार चुनें</option>
                    <option value="e-rickshaw">ई-रिक्शा</option>
                    <option value="bike">बाइक</option>
                    <option value="auto">ऑटो</option>
                </select>

                <label for="pincode">सेवा क्षेत्र पिनकोड:</label>
                <input type="text" id="pincode" name="pincode" required>

                <label for="mobile">मोबाइल नंबर:</label>
                <input type="tel" id="mobile" name="mobile" required>

                <label for="referralCode">रेफरल कोड:</label>
                <input type="text" id="referralCode" name="referralCode" value="Mahakumbh25" readonly>

                <label for="drivingLicense">ड्राइविंग लाइसेंस (PDF, JPG, या PNG):</label>
                <input type="file" id="drivingLicense" name="drivingLicense" accept=".pdf,.jpg,.jpeg,.png" required>

                <label for="aadhaar">आधार (PDF, JPG, या PNG):</label>
                <input type="file" id="aadhaar" name="aadhaar" accept=".pdf,.jpg,.jpeg,.png" required>

                <div class="checkbox-container">
                    <input type="checkbox" id="termsAccept" name="termsAccept" required>
                    <label for="termsAccept">मैं नियम और शर्तों को स्वीकार करता हूं</label>
                </div>

                <button type="submit"> SAVE </button>
            </form>
        </div>
    </div>

    <script>
        document.getElementById('serviceProviderForm').addEventListener('submit', async function(e) {
            e.preventDefault();
            
            if (!document.getElementById('termsAccept').checked) {
                alert('कृपया नियम और शर्तों को स्वीकार करें।');
                return;
            }

            const formData = {
                name: document.getElementById('name').value,
                vehicleType: document.getElementById('vehicleType').value,
                pincode: document.getElementById('pincode').value,
                mobile: document.getElementById('mobile').value,
                referralCode: document.getElementById('referralCode').value,
                drivingLicense: document.getElementById('drivingLicense').files[0] ? document.getElementById('drivingLicense').files[0].name : '',
                aadhaar: document.getElementById('aadhaar').files[0] ? document.getElementById('aadhaar').files[0].name : '',
                submissionDateTime: new Date().toISOString()
            };

            try {
                const response = await fetch('https://script.google.com/macros/s/AKfycbyFW_nfCI_JV39OVQzHRGzTvnOjSkTtdrIiu2xgKbCpFKo9RCW076nc2oZmGA-gIlxD/exec', {
                    method: 'POST',
                    mode: 'no-cors',
                    headers: {
                        'Content-Type': 'application/json',
                    },
                    body: JSON.stringify(formData)
                });

                alert('फॉर्म सफलतापूर्वक जमा किया गया!');
                this.reset();
                document.getElementById('referralCode').value = 'Mahakumbh25';
            } catch (error) {
                console.error('Error:', error);
                alert('फॉर्म जमा करने में त्रुटि हुई। कृपया पुनः प्रयास करें।');
            }
        });
    </script>
</body>
</html>
