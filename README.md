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
    to
