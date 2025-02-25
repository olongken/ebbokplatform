# ebookshopy
Laman web ini merupakan platform jualan eBook digital yang menawarkan buku interaktif dalam pelbagai kategori. Ia direka dengan tema kontemporari, mesra pengguna, dan mudah diakses. Pengguna boleh melihat katalog eBook, membuat tempahan, dan melakukan pembayaran secara online dengan mudah.
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>eBook Digital Platform</title>
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
        header {
            background: #333;
            color: white;
            padding: 20px;
            animation: fadeIn 1.5s ease-in-out;
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
        .ebook-list {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 20px;
        }
        .ebook {
            background: white;
            padding: 15px;
            border-radius: 5px;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease-in-out;
        }
        .ebook:hover {
            transform: translateY(-5px);
        }
        form {
            background: white;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
            max-width: 400px;
            margin: 20px auto;
        }
        input, select, button {
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
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
    </style>
</head>
<body>
    <header>
        <h1>Buku Digital & eBook Interaktif</h1>
        <p>Tempat terbaik untuk mendapatkan eBook berkualiti dengan elemen interaktif!</p>
        <a href="#shop" class="btn">Beli Sekarang</a>
    </header>
    
    <section id="shop">
        <h2>Katalog eBook</h2>
        <div class="ebook-list">
            <div class="ebook">
                <img src="ebook1.jpg" alt="eBook 1">
                <h3>Asas Seni Visual</h3>
                <p>Pelajari asas seni dengan modul lengkap dan interaktif.</p>
                <a href="#order" class="btn">Tempah Sekarang</a>
            </div>
            <div class="ebook">
                <img src="ebook2.jpg" alt="eBook 2">
                <h3>Seni & Penceritaan</h3>
                <p>Menggabungkan seni dan naratif untuk pengalaman pembelajaran unik.</p>
                <a href="#order" class="btn">Tempah Sekarang</a>
            </div>
        </div>
    </section>
    
    <section id="order">
        <h2>Borang Tempahan</h2>
        <form id="orderForm">
            <input type="text" id="name" placeholder="Nama Penuh" required>
            <input type="email" id="email" placeholder="Email" required>
            <select id="ebookChoice" required>
                <option value="">Pilih eBook</option>
                <option value="Asas Seni Visual">Asas Seni Visual</option>
                <option value="Seni & Penceritaan">Seni & Penceritaan</option>
            </select>
            <button type="submit">Buat Tempahan</button>
        </form>
    </section>
    
    <section id="contact">
        <h2>Hubungi Kami</h2>
        <p>Email: support@ebookplatform.com</p>
        <p>WhatsApp: +6012-3456789</p>
    </section>
    
    <footer>
        <p>&copy; 2025 eBook Digital Platform. Hak cipta terpelihara.</p>
    </footer>
    
    <script>
        document.addEventListener("DOMContentLoaded", function() {
            document.getElementById("orderForm").addEventListener("submit", function(event) {
                event.preventDefault();
                
                let name = document.getElementById("name").value;
                let email = document.getElementById("email").value;
                let ebook = document.getElementById("ebookChoice").value;
                
                if (ebook) {
                    let paymentUrl = `https://www.billplz.com/pay?name=${encodeURIComponent(name)}&email=${encodeURIComponent(email)}&ebook=${encodeURIComponent(ebook)}`;
                    window.location.href = paymentUrl;
                } else {
                    alert("Sila pilih eBook terlebih dahulu.");
                }
            });
        });
    </script>
</body>
</html>
