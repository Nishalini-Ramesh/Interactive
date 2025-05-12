# Ex.08 Design of Interactive Image Gallery
## Date:12/05/25

## AIM:
To design a web application for an inteactive image gallery with minimum five images.

## DESIGN STEPS:

### Step 1:
Clone the github repository and create Django admin interface.

### Step 2:
Change settings.py file to allow request from all hosts.

### Step 3:
Use CSS for positioning and styling.

### Step 4:
Write JavaScript program for implementing interactivity.

### Step 5:
Validate the HTML and CSS code.

### Step 6:
Publish the website in the given URL.

## PROGRAM :
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Photo Gallery</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>NISHALINI R</h1>
        <h2>Register Number: 212224040222</h2>
        
    </header>
    <div class="gallery">
        <img src="./image1.jpg" alt="Image 1">
        <img src="./image2.jpg" alt="Image 2">
        <img src="./image3.jpg" alt="Image 3">
        <img src="./image4.jpg" alt="Image 4">
        <img src="./image5.jpg" alt="Image 5">
        <img src="./image6.jpg"alt="Image 6">
        <img src="./image7.jpg"alt="Image 7">
        <img src="./image8.webp"alt="Image 8">
        <img src="./image9.jpg"alt="Image 9">
        <img src="./image10.jpg"alt="Image 10">

        
    </div>

    <div class="modal" id="modal">
        <span class="close" id="close">&times;</span>
        <span class="nav prev" id="prev">&#10094;</span>
        <img id="modal-img" src="" alt="">
        <span class="nav next" id="next">&#10095;</span>
    </div>

    <script src="script.js"></script>
</body>
</html>

const gallery = document.querySelectorAll('.gallery img');
const modal = document.getElementById('modal');
const modalImg = document.getElementById('modal-img');
const closeBtn = document.getElementById('close');
const prevBtn = document.getElementById('prev');
const nextBtn = document.getElementById('next');

let currentIndex = 0;

const showModal = (index) => {
    modal.style.display = 'flex';
    modalImg.src = gallery[index].src;
    currentIndex = index;
};

gallery.forEach((img, index) => {
    img.addEventListener('click', () => showModal(index));
});

closeBtn.addEventListener('click', () => {
    modal.style.display = 'none';
});

prevBtn.addEventListener('click', () => {
    currentIndex = (currentIndex - 1 + gallery.length) % gallery.length;
    modalImg.src = gallery[currentIndex].src;
});

nextBtn.addEventListener('click', () => {
    currentIndex = (currentIndex + 1) % gallery.length;
    modalImg.src = gallery[currentIndex].src;
});

window.addEventListener('click', (e) => {
    if (e.target === modal) {
        modal.style.display = 'none';
    }
});




```

## OUTPUT:

![alt text](<intpro/intapp/static/Screenshot 2025-05-12 105231.png>)

![alt text](<intpro/intapp/static/Screenshot 2025-05-12 105252.png>)

## RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
