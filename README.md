# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks

Create a CSS animation.
Store data in localStorage.
Apply JavaScript to trigger animations.

Happy Coding! 💻✨

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Interactive CSS3 & JavaScript Page</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: white;
      color: black;
      transition: background-color 0.5s, color 0.5s;
      text-align: center;
      margin-top: 100px;
    }

    body.dark-mode {
      background-color: #121212;
      color: white;
    }

    button {
      padding: 10px 20px;
      font-size: 16px;
      margin: 10px;
      cursor: pointer;
      transition: transform 0.3s ease;
    }

    /* Animation class */
    .animate {
      animation: pulse 0.6s ease;
    }

    /* Keyframes */
    @keyframes pulse {
      0% { transform: scale(1); }
      50% { transform: scale(1.2); }
      100% { transform: scale(1); }
    }
  </style>
</head>
<body>
  <h1>Welcome to the Interactive Page!</h1>
  <button id="animateBtn">Animate Me</button>
  <button id="themeBtn">Toggle Dark Mode</button>

  <script>
    // Load theme from localStorage
    document.addEventListener('DOMContentLoaded', () => {
      const savedTheme = localStorage.getItem('theme');
      if (savedTheme === 'dark') {
        document.body.classList.add('dark-mode');
      }
    });

    // Animate button
    document.getElementById('animateBtn').addEventListener('click', () => {
      const btn = document.getElementById('animateBtn');
      btn.classList.add('animate');
      
      btn.addEventListener('animationend', () => {
        btn.classList.remove('animate');
      }, { once: true });
    });

    // Toggle theme and save to localStorage
    document.getElementById('themeBtn').addEventListener('click', () => {
      document.body.classList.toggle('dark-mode');
      const isDark = document.body.classList.contains('dark-mode');
      localStorage.setItem('theme', isDark ? 'dark' : 'light');
    });
  </script>
</body>
</html>
