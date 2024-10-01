<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Galería de Fotos y Vídeos</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Galería de Fotos y Vídeos</h1>
        <nav>
            <a href="#fotos">Fotos</a>
            <a href="#videos">Vídeos</a>
            <a href="#subir">Subir Contenido</a>
        </nav>
    </header>

    <section id="fotos">
        <h2>Fotos</h2>
        <div class="gallery" id="photo-gallery">
            <!-- Aquí se mostrarán las fotos subidas -->
        </div>
    </section>

    <section id="videos">
        <h2>Vídeos</h2>
        <div class="gallery" id="video-gallery">
            <!-- Aquí se mostrarán los vídeos subidos -->
        </div>
    </section>

    <section id="subir">
        <h2>Subir Contenido</h2>
        <form id="uploadForm">
            <label for="file">Subir archivo:</label>
            <input type="file" id="file" accept="image/*,video/*" required>
            <button type="submit">Subir</button>
        </form>
    </section>

    <footer>
        <p>© 2024 Galería Personal</p>
    </footer>

    <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f4f4f4;
}

header {
    background-color: #333;
    color: white;
    padding: 10px;
    text-align: center;
}

nav a {
    color: white;
    margin: 0 15px;
    text-decoration: none;
}

h1, h2 {
    color: #333;
}

section {
    padding: 20px;
    text-align: center;
}

.gallery {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 10px;
    padding: 20px;
}

.gallery img, .gallery video {
    width: 100%;
    height: auto;
    border-radius: 8px;
}

footer {
    background-color: #333;
    color: white;
    text-align: center;
    padding: 10px;
    position: relative;
    width: 100%;
    bottom: 0;
}
document.getElementById('uploadForm').addEventListener('submit', function (e) {
    e.preventDefault();
    
    const fileInput = document.getElementById('file');
    const file = fileInput.files[0];

    if (file) {
        const reader = new FileReader();
        reader.onload = function (e) {
            const fileURL = e.target.result;
            const gallery = file.type.startsWith('image/') ? 'photo-gallery' : 'video-gallery';
            const galleryElement = document.getElementById(gallery);

            if (file.type.startsWith('image/')) {
                const img = document.createElement('img');
                img.src = fileURL;
                galleryElement.appendChild(img);
            } else if (file.type.startsWith('video/')) {
                const video = document.createElement('video');
                video.src = fileURL;
                video.controls = true;
                galleryElement.appendChild(video);
            }
        };
        reader.readAsDataURL(file);
    }
});
