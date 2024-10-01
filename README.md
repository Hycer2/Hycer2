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
