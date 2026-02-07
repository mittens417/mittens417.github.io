---
layout: default
title: Be My Valentine
---

<style>
  body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: #ffeef2; /* Light pink background */
    text-align: center;
    color: #d6336c;
    margin: 0;
    padding-bottom: 50px;
  }

  /* Hero Section Styles */
  .valentine-container {
    height: 90vh; /* Takes up most of the screen */
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  h1 {
    font-size: 3rem;
    margin-bottom: 20px;
    animation: heartbeat 1.5s infinite;
  }

  /* The YES Button */
  .yes-btn {
    background-color: #ff477e;
    color: white;
    border: none;
    padding: 15px 40px;
    font-size: 1.5rem;
    border-radius: 50px;
    cursor: pointer;
    box-shadow: 0 4px 15px rgba(255, 71, 126, 0.4);
    transition: transform 0.2s;
  }

  .yes-btn:hover {
    transform: scale(1.1);
    background-color: #ff0a54;
  }

  /* Carousel Section Styles */
  #memories {
    display: none; /* Hidden until YES is clicked */
    padding: 20px;
    opacity: 0;
    transition: opacity 1s ease-in;
  }

  .carousel-container {
    max-width: 600px;
    margin: 0 auto;
    position: relative;
    border-radius: 15px;
    overflow: hidden;
    box-shadow: 0 10px 25px rgba(0,0,0,0.1);
  }

  .slide {
    display: none;
    width: 100%;
  }
  
  .slide img {
    width: 100%;
    height: 400px;
    object-fit: cover;
  }

  .active-slide {
    display: block;
    animation: fade 0.5s;
  }

  /* Carousel Navigation Buttons */
  .prev, .next {
    cursor: pointer;
    position: absolute;
    top: 50%;
    width: auto;
    margin-top: -22px;
    padding: 16px;
    color: white;
    font-weight: bold;
    font-size: 18px;
    transition: 0.6s ease;
    border-radius: 0 3px 3px 0;
    background-color: rgba(0,0,0,0.3);
    border: none;
  }

  .next {
    right: 0;
    border-radius: 3px 0 0 3px;
  }
  
  .prev {
    left: 0;
    border-radius: 3px 0 0 3px;
  }

  @keyframes heartbeat {
    0% { transform: scale(1); }
    50% { transform: scale(1.05); }
    100% { transform: scale(1); }
  }
  
  @keyframes fade {
    from {opacity: .4} 
    to {opacity: 1}
  }
</style>

<div class="valentine-container">
  <h1>Will you be my Valentine? 🌹</h1>
  <button class="yes-btn" onclick="showSuccess()">YES</button>
</div>

<div id="memories">
  <h2>Yay! Here are some of my favorite memories:</h2>
  
  <div class="carousel-container">
    
  <div class="slide active-slide">
      <img src="https://images.unsplash.com/photo-1518568814500-bf0f8d125f46?q=80&w=1000&auto=format&fit=crop" alt="Memory 1">
    </div>

  <div class="slide">
      <img src="https://images.unsplash.com/photo-1516589178581-6cd7833ae3b2?q=80&w=1000&auto=format&fit=crop" alt="Memory 2">
  </div>

  <div class="slide">
      <img src="https://images.unsplash.com/photo-1529333166437-7750a6dd5a70?q=80&w=1000&auto=format&fit=crop" alt="Memory 3">
  </div>

  <button class="prev" onclick="changeSlide(-1)">&#10094;</button>
  <button class="next" onclick="changeSlide(1)">&#10095;</button>
  </div>
</div>

<script>
  // Function to reveal the carousel when YES is clicked
  function showSuccess() {
    const memorySection = document.getElementById('memories');
    memorySection.style.display = 'block';
    
    // Smooth fade in
    setTimeout(() => {
      memorySection.style.opacity = 1;
    }, 50);

    // Scroll down to the carousel
    memorySection.scrollIntoView({ behavior: 'smooth' });
    
    // Optional: Change the header text
    document.querySelector('h1').innerText = "I knew you'd say yes! ❤️";
    document.querySelector('.yes-btn').style.display = 'none';
  }

  // Carousel Logic
  let slideIndex = 1;

  function changeSlide(n) {
    showSlides(slideIndex += n);
  }

  function showSlides(n) {
    let i;
    let slides = document.getElementsByClassName("slide");
    
    if (n > slides.length) {slideIndex = 1}
    if (n < 1) {slideIndex = slides.length}
    
    for (i = 0; i < slides.length; i++) {
      slides[i].style.display = "none";
      slides[i].className = slides[i].className.replace(" active-slide", "");
    }
    
    slides[slideIndex-1].style.display = "block";
    slides[slideIndex-1].className += " active-slide";
  }
</script>
