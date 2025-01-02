# Ex.08 Design of Interactive Image Gallery

## AIM
  To design a web application for an inteactive image gallery with minimum five images.

## DESIGN STEPS

## Step 1:

Clone the github repository and create Django admin interface

## Step 2:

Change settings.py file to allow request from all hosts.

## Step 3:

Use CSS for positioning and styling.

## Step 4:

Write JavaScript program for implementing interactivit

## Step 5:

Validate the HTML and CSS code

## Step 6:

Publish the website in the given URL.

## PROGRAM

```
<html>
    <head>
    <title>Image Gallery</title>
    <style>
        body {
           
    font-family: 'Arial', sans-serif;
    margin: 0;
    padding: 0;
    background-color: #20d18a; /* Light blue */
    display: flex;
    flex-direction: column;
    align-items: center;
    min-height: 100vh;
}

        

        .header {
            text-align: center;
            padding: 10px;
            background-color: #3018bba4;
            width: 100%;
            height:100px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            font-family:monospace;
        
        }

        .header h1 {
            font-size: 2.5rem;
            color: #c3bfc0;
        }

        .header p {
            font-size: 1.2rem;
            color: #292d5f;
        }

        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 15px;
            padding: 20px;
            margin: 20px 0 10px 0;
            width: 90%;
            max-width: 1200px;
        }

        .gallery-item {
            border-radius: 10px;
            overflow: hidden;
            position: relative;
            cursor: pointer;
            border: 10px solid #4b46ee;
            margin-right: 40px;
        }

        .gallery-item img {
            width: 100%;
            height:100%;
            object-fit: cover;
            display: block;
        }

        .gallery-item:nth-child(1) {
            grid-column: span 4;
            grid-row: span 2;
        }

        .gallery-item:nth-child(2) {
            grid-column: span 3;
            grid-row: span 2;
        }


        .gallery-item:nth-child(3) {
            grid-column: span 3;
            grid-row: span 1;
        }

        .gallery-item:nth-child(4) {
            grid-column: span 3;
            grid-row: span 1;
        }
        .gallery-item:nth-child(5) {
            grid-column: span 4;
            grid-row: span 1;
        }

        .gallery-item:nth-child(6) {
            grid-column: span 3;
        }
        .gallery-item:nth-child(7) {
            grid-column: span 2;
            grid-row: span 2;
        }
        .gallery-item:nth-child(8) {
            grid-column: span 5;
            grid-row: span 2;
        }

        .gallery-item::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(to bottom right, rgba(255, 255, 255, 0.2), rgba(0, 0, 0, 0.2));
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .gallery-item:hover::after {
            opacity: 1;
        }

        .footer {
            text-align: center;
            margin-top: 20px;
            padding: 10px;
            width: 100%;
            height:40px;
            background-color: #744670;
        }

        .footer p{
            font-size: 1.2rem;
            color: #000000;
        }

        #lightbox {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            justify-content: center;
            align-items: center;
            z-index: 1000;
        }

        #lightbox img {
            max-width: 90%;
            max-height: 80%;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5);
        }

        #lightbox:target {
            display: flex;
        }

        #lightbox .close {
            position: absolute;
            top: 10px;
            right: 10px;
            background: #281994;
            border: none;
            font-size: 2rem;
            cursor: pointer;
        }
    </style>
</head>
<body>

<div class="header">
    <h1>Image Gallery</h1>
   
</div>

<div class="gallery">
    <div class="gallery-item" onclick="showAlert('Image 1 clicked!')">
        <img src="" alt="Image 1">
    </div>
    <div class="gallery-item" onclick="showAlert('Image 2 clicked!')">
        <img src="img2.jpg" alt="Image 2" >
    </div>
    <div class="gallery-item" onclick="showAlert('Image 3 clicked!')">
        <img src="img3.jpg"alt="Image 3">
    </div>
    <div class="gallery-item" onclick="showAlert('Image 4 clicked!')">
        <img src="img4.jpg" alt="Image 4">
    </div>
    <div class="gallery-item" onclick="showAlert('Image 5 clicked!')">
        <img src="imgult..jpg" alt="Image 5">
    </div>
    <div class="gallery-item" onclick="showAlert('Image 6 clicked!')">
        <img src="img6.jpg" alt="Image 6">
    </div>
    <div class="gallery-item" onclick="showAlert('Image 7 clicked!')">
        <img src="img7.jpg"  alt="Image 7">
    </div>
    
    <div class="gallery-item" onclick="showAlert('Image 8 clicked!')">
        <img src="img5.jpg" alt="Image 8">
    </div>
</div>

<div id="lightbox">
    <button class="close" onclick="closeLightbox()">&#215;</button>

    <img src="" id="lightbox-img" alt="Full Image">
</div>

<div class="footer">
    <p><b>Designed by Sai Hrishi(24900846)</b></p>
</div>

<script>
    function showAlert(message) {
        alert(message);
    }

    function openLightbox(imageSrc) {
        document.getElementById('lightbox-img').src = imageSrc;
        document.getElementById('lightbox').style.display = 'flex';
    }

    function closeLightbox() {
        document.getElementById('lightbox').style.display = 'none';
    }

    const galleryItems = document.querySelectorAll('.gallery-item');
    galleryItems.forEach(item => {
        item.addEventListener('click', () => {
            const imgSrc = item.querySelector('img').src;
            openLightbox(imgSrc);
        });
    });
</script>

</body>
</html>
```

## OUTPUT

![alt text](<Screenshot 2025-01-02 021859.png>)

![alt text](<Screenshot 2025-01-02 021918.png>)

![alt text](<Screenshot 2025-01-02 021947.png>)

![alt text](<Screenshot 2025-01-02 022008.png>)

![alt text](<Screenshot 2025-01-02 022023.png>)

## RESULT
  The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
