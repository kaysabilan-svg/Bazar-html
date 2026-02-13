<pDOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bazar Makanan Sekolah</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap" rel="stylesheet"> <!-- Google Fonts -->
    <style>
        body {
            font-family: 'Poppins', sans-serif;
            margin: 0;
            padding: 0;
            background: url('https://source.unsplash.com/featured/?school-food') no-repeat center center fixed; /* Latar belakang gambar makanan sekolah dari Unsplash */
            background-size: cover;
            color: #333;
        }
        header {
            background-color: rgba(255, 165, 0, 0.9); /* Oranye transparan */
            color: white;
            text-align: center;
            padding: 20px;
        }
        .container {
            max-width: 1200px;
            margin: 20px auto;
            padding: 20px;
            background-color: rgba(255, 255, 255, 0.9); /* Putih transparan */
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
        .menu {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-around;
        }
        .item {
            background-color: #f9f9f9;
            border: 1px solid #ddd;
            border-radius: 10px;
            margin: 10px;
            padding: 15px;
            width: 300px;
            text-align: center;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        .item img {
            width: 100%;
            height: 150px;
            object-fit: cover;
            border-radius: 10px;
        }
        button {
            background-color: #28a745;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background-color: #218838;
        }
        #map {
            height: 300px;
            width: 100%;
            border-radius: 10px;
            margin-top: 20px;
        }
        #qr-section {
            text-align: center;
            margin-top: 20px;
        }
        #qrcode {
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <header>
        <h1>Selamat Datang di Bazar Makanan Sekolah!</h1>
        <p>Makanan lezat dan sehat untuk siswa. Pesan sekarang!</p>
    </header>
    
    <div class="container">
        <h2>Menu Makanan</h2>
        <div class="menu">
            <div class="item">
                <img src="https://source.unsplash.com/featured/?nasi-goreng" alt="Nasi Goreng">
                <h3>Nasi Goreng</h3>
                <p>Nasi goreng spesial sekolah dengan telur dan sayuran.</p>
                <p><strong>Rp 15.000</strong></p>
                <button>Pesan</button>
            </div>
            <div class="item">
                <img src="https://source.unsplash.com/featured/?mie-goreng" alt="Mie Goreng">
                <h3>Mie Goreng</h3>
                <p>Mie goreng pedas dengan ayam dan sayuran.</p>
                <p><strong>Rp 12.000</strong></p>
                <button>Pesan</button>
            </div>
            <div class="item">
                <img src="https://source.unsplash.com/featured/?jus-buah" alt="Jus Buah">
                <h3>Jus Buah Segar</h3>
                <p>Jus jeruk atau mangga segar untuk penyegar.</p>
                <p><strong>Rp 8.000</strong></p>
                <button>Pesan</button>
            </div>
        </div>
        
        <h2>Lokasi Bazar</h2>
        <div id="map"></div> <!-- Google Maps embed -->
        
        <div id="qr-section">
            <h2>Scan QR untuk Akses Cepat</h2>
            <button onclick="generateQR()">Generate QR Code</button>
            <div id="qrcode"></div>
        </div>
    </div>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script> <!-- Library QR Code -->
    <script>
        // Google Maps initialization
        function initMap() {
            const location = { lat: -6.2088, lng: 106.8456 }; // Koordinat Jakarta (ganti dengan lokasi sekolah Anda, e.g., lat/lng dari Google Maps)
            const map = new google.maps.Map(document.getElementById("map"), {
                zoom: 15,
                center: location,
            });
            const marker = new google.maps.Marker({
                position: location,
                map: map,
                title: "Bazar Makanan Sekolah",
            });
        }

        

        // Generate QR Code
        function generateQR() {
            const url = window.location.href; // URL website ini
            document.getElementById('qrcode').innerHTML = ''; // Clear previous QR
            new QRCode(document.getElementById('qrcode'), {
                text: url,
                width: 128,
                height: 128,
            });
        }
    </script>
</body>
</html>
