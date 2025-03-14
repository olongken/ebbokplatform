<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Admin Panel - Pengurusan eBook</title>
    <link rel="stylesheet" href="styles.css">
    <script defer src="admin.js"></script>
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
        input, button {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        button {
            background: #ff6600;
            color: white;
            border: none;
            cursor: pointer;
        }
        button:hover {
            background: #ff4500;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Admin Panel - Tambah eBook</h1>
        <input type="text" id="ebookTitle" placeholder="Tajuk eBook">
        <input type="text" id="ebookFile" placeholder="URL eBook">
        <button onclick="addEbook()">Tambah eBook</button>
        <h2>Senarai eBook</h2>
        <ul id="ebookList"></ul>
    </div>
    
    <script>
        document.addEventListener("DOMContentLoaded", function() {
            loadEbooks();
        });
        
        function addEbook() {
            let title = document.getElementById("ebookTitle").value;
            let file = document.getElementById("ebookFile").value;
            
            if (title && file) {
                let ebooks = JSON.parse(localStorage.getItem("ebooks")) || {};
                ebooks[title.toLowerCase().replace(/\s+/g, '')] = file;
                localStorage.setItem("ebooks", JSON.stringify(ebooks));
                alert("eBook berjaya ditambah!");
                loadEbooks();
            } else {
                alert("Sila isi semua maklumat.");
            }
        }
        
        function loadEbooks() {
            let ebooks = JSON.parse(localStorage.getItem("ebooks")) || {};
            let list = document.getElementById("ebookList");
            list.innerHTML = "";
            
            for (let key in ebooks) {
                let li = document.createElement("li");
                li.textContent = `${key} - ${ebooks[key]}`;
                list.appendChild(li);
            }
        }
    </script>
</body>
</html>

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
            const urlParams = new URLSearchParams(window.location.search);
            const ebook = urlParams.get("ebook");
            
            let downloadLinks = JSON.parse(localStorage.getItem("ebooks")) || {
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
