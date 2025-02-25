<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Muat Turun eBook</title>
    <link rel="stylesheet" href="styles.css">
    <script defer src="script.js"></script>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            text-align: center;
            background-color: #f4f4f4;
        }
        .container {
            max-width: 600px;
            margin: 50px auto;
            background: white;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
        }
        h1 {
            color: #333;
        }
        .btn {
            display: inline-block;
            padding: 10px 20px;
            margin: 10px;
            background: #ff6600;
            color: white;
            text-decoration: none;
            border-radius: 5px;
            transition: transform 0.2s ease-in-out;
        }
        .btn:hover {
            transform: scale(1.1);
            background-color: #ff4500;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Muat Turun eBook Anda</h1>
        <p>Terima kasih kerana membeli eBook kami! Klik butang di bawah untuk memuat turun eBook anda.</p>
        <div id="downloadSection">
            <a id="downloadLink" href="#" class="btn">Muat Turun eBook</a>
        </div>
        <p>Jika terdapat sebarang masalah, sila hubungi kami di <b>support@ebookplatform.com</b></p>
    </div>
    
    <script>
        document.addEventListener("DOMContentLoaded", function() {
            // Dapatkan parameter dari URL
            const urlParams = new URLSearchParams(window.location.search);
            const ebook = urlParams.get("ebook");
            
            // Tetapkan pautan muat turun berdasarkan eBook yang dibeli
            let downloadLinks = {
                "asasseni": "ebooks/asas-seni-visual.pdf",
                "senipenceritaan": "ebooks/seni-penceritaan.pdf"
            };
            
            if (downloadLinks[ebook]) {
                document.getElementById("downloadLink").href = downloadLinks[ebook];
            } else {
                document.getElementById("downloadSection").innerHTML = "<p>Maaf, eBook tidak ditemui. Sila hubungi sokongan.</p>";
            }
        });
    </script>
</body>
</html>
