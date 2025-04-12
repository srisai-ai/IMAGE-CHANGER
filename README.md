<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Image Changer</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 50px;
        }
        .image-container {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }
        img {
            width: 900px;
            height: 600px;
            object-fit: cover;
        }
        button {
            padding: 10px 15px;
            font-size: 16px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div class="image-container">
        <button onclick="prevImage()">Previous</button>
        <img id="displayImage" src="image1.jpg" alt="Image">
        <button onclick="nextImage()">Next</button>
    </div>

    <script>
        const images = ["image1.jpg", "image2.jpg", "image8.webp"];
        let currentIndex = 0;

        function updateImage() {
            document.getElementById("displayImage").src = images[currentIndex];
        }

        function nextImage() {
            currentIndex = (currentIndex + 1) % images.length;
            updateImage();
        }

        function prevImage() {
            currentIndex = (currentIndex - 1 + images.length) % images.length;
            updateImage();
        }
    </script>
</body>
</html>
